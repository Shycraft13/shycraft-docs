# Cross-server & Proxy

staffcore is designed to run on a whole network out of the box: every ban, unban, mute, unmute and kick propagates to every other backend and the proxy, and staff commands tab-complete across the whole network.

This page walks through the three layers that make it work:

1. **Shared database** the source of truth. Required for cross-server.
2. **Redis event bus** optional real-time layer.
3. **Velocity proxy** optional edge-enforcement layer.

## 1. Shared database (required)

The network must share a **single** MySQL/MariaDB or MongoDB instance. SQLite works only for single-server setups.

- Every backend AND the proxy point their `config/database.yml` at the same database.
- Tables are created by the first backend that starts up; the proxy reads and writes the same rows.
- Every ban / unban / mute / unmute / kick appends a row to a shared event log.
- Every node keeps a cursor into that log and polls new rows every `cross-server.poll-interval-seconds` (default: 5 seconds).

That alone gives you full cross-server functionality with a few seconds of latency.

## 2. Redis event bus (optional, real-time)

If you enable Redis (in `config/database.yml`, `redis:` block), every node also PUBLISHes on `<channel-prefix>:events` and SUBSCRIBES to it. Now every event arrives in milliseconds instead of on the next poll tick.

Design invariants:

- **The database is still the source of truth.** Redis is only a wake-up signal. Every writer writes to the DB first, then publishes.
- **Loss-tolerant.** Redis pub/sub is at-most-once: an offline subscriber misses the message. The DB event poller catches up on the next tick.
- **Origin filter.** Every message carries `origin = server-id`. Subscribers drop matches (so a backend doesn't act on its own broadcast).
- **Dedicated subscriber thread + reconnect.** The subscribe call blocks, so the bus owns a daemon thread with exponential backoff (1s → 5s → 30s cap).
- **Keep Redis private.** TLS is not wired up. Do not expose Redis to the internet.

If Redis is on but momentarily unreachable, the DB poller still catches every event. You lose latency, not correctness.

## 3. Velocity proxy delegation (optional, edge-enforcement)

Without the proxy, a ban is enforced by the backend that receives the command via `player.kick()`. That works, but on a networked setup there's a small window where a banned player could re-log onto a different backend before the kick lands.

With the proxy JAR installed:

```yaml
# config/config.yml on every backend
proxy:
  enabled: true
  wait-for-proxy: true
  timeout-ms: 2000
```

...ban, unban and kick commands hand the decision to the proxy. The proxy writes the DB row (or performs the edge disconnect for kicks) and replies. Meanwhile the client-facing socket is on the proxy, so disconnecting there wins every race.

If Redis is enabled, the plugin uses an even shorter fast-path: the backend writes the DB + publishes on Redis, the proxy's Redis subscriber sees the event and disconnects the target within milliseconds. No plugin-message round trip.

Fallback behaviour:

- Proxy on, Redis on → Redis fast path.
- Proxy on, Redis off, `wait-for-proxy: true` → plugin-message round trip.
- Proxy on, Redis off, `wait-for-proxy: false` → fire-and-forget plugin message + local kick.
- Proxy off → local kick / DB write only. Cross-server events still propagate via the DB poller (and Redis if enabled).

## Server-id (required for cross-server)

Every node needs a unique `server-id`:

- **Backends**: `staffcore.server-id` in `plugins/StaffCore/config/config.yml`.
- **Proxy**: `server-id` at the top of `plugins/staffcoreproxy/config/config.yml`.

Recommended: short, alphanumeric, lowercase. Examples: `smp1`, `creative`, `lobby`, `proxy-a`.

If left empty, staffcore logs a WARNING and falls back to a per-boot random UUID. Everything still works, but you lose the stable identity used for audit trails, `/staffcore push` targeting, and node discovery.

## Config push

`/staffcore push` copies configs from one node to one or many other nodes over Redis. Requires Redis to be enabled network-wide.

Presets:

| Preset | What gets copied |
| --- | --- |
| `punishments` | `punishments/**` (templates, messages, screens, sounds, GUIs) |
| `database` | `config/database.yml`, `config/permissions.yml` |
| `gui` | `punishments/gui/**`, `punishments/screens.yml`, `punishments/messages.yml`, `punishments/sounds.yml` |
| `all` | Everything except `config/config.yml` |

`config/config.yml` is **never** pushed because it holds per-node identity (`server-id`, proxy toggles, per-node overrides). This rule is enforced on both send and receive.

The source is always explicit: the `<from>` argument names the node whose configs get read. Any live node can be picked, not just the current one. When `<from>` is not the current node, the command publishes a request on `<prefix>:pushes:request`; the named source node subscribes on that channel, reads its own configs, and publishes them on `<prefix>:pushes:announce` as if it had been called there directly.

Two ways to invoke:

- `/staffcore push` (no args, as a player) opens a GUI: pick source node → pick target servers → pick preset → confirm.
- `/staffcore push <from> <to|*> <preset>` scripted mode. Unknown server-ids are rejected upfront so a typo doesn't silently succeed. `<from>` and `<to>` must differ. When run by a player, the scripted variant still opens the confirm stage of the GUI so a chat typo cannot push by accident. Append `--yes` (alias `-y`) to skip the confirm — required for automation, shell scripts and cron. Console callers always skip. The confirm GUI layout is customizable in [`push/confirm.yml`](configuration/push/confirm.md).

Node discovery works via Redis heartbeats: every node writes a short-lived key `<prefix>:nodes:<server-id>` with a 30-second TTL, refreshed every 10 seconds. The GUI reads these to list live nodes.

Backends apply pushed configs by soft-reloading (same as `/staffcore reload`). The proxy writes the files to disk but does not soft-reload; restart the proxy to apply.

## JAR update

`/staffcore update` ships the running StaffCore JAR from one node to one
or many other nodes over Redis. Requires Redis to be enabled
network-wide.

The source is always explicit: the `<from>` argument names the node
whose JAR gets shipped. When `<from>` is not the current node, the
command publishes a request on `<prefix>:updates:request`; the named
source node subscribes on that channel and does the actual read + send
on its side, exactly as if the command had been typed there.

The source reads its running JAR, computes a SHA-256, wraps the bytes in
a single-entry ZIP, base64-encodes and stores at
`<prefix>:updates:payload:<update-id>` with a 15-minute TTL, then
publishes an announce on `<prefix>:updates:announce`. Every subscriber
whose server-id matches (`*` = everyone, otherwise exact match) fetches
the payload, verifies size + SHA-256, and writes the JAR atomically to
`plugins/update/<jarname>.jar`.

Bukkit's built-in `plugins/update/` folder means the file is atomically
swapped in on the receiver's next server restart. StaffCore does not
force the restart. Each node reboots on its own schedule. Missing
config files or folders the new JAR ships are recreated by
`ResourceUpdater` on that first enable, so a node that was on an older
version catches up on its own.

The receiver rejects the JAR before writing if:

- The payload key has expired (TTL passed before the receiver was
  online).
- The unzipped size doesn't match the announced `sizeBytes`.
- The SHA-256 doesn't match the announced digest.

Two ways to invoke:

- `/staffcore update` (no args, as a player) opens a GUI: pick source
  node → pick target servers → confirm.
- `/staffcore update <from> <to|*>` scripted mode. Unknown server-ids
  are rejected upfront. `<from>` and `<to>` must differ. When run by a
  player, the scripted variant still opens the confirm stage of the
  GUI so a chat typo cannot ship a JAR by accident. Append `--yes`
  (alias `-y`) to skip the confirm, required for automation, shell
  scripts and cron. Console callers always skip. The confirm GUI
  layout is customizable in
  [`update/confirm.yml`](configuration/update/confirm.md).

Node discovery reuses the same `<prefix>:nodes:<server-id>` heartbeat
keys as `/staffcore push`; the GUI lists every node that has published
a heartbeat within the last 30 seconds.

## Payload types

Every cross-server event carries one of these types, both on the DB log and on Redis:

| Type | Fires on |
| --- | --- |
| `BAN` | `/ban`, `/punish` with a ban-category template |
| `UNBAN` | `/unban` |
| `MUTE` | `/mute`, `/punish` with a mute-category template |
| `UNMUTE` | `/unmute` |
| `KICK` | `/kick`, `/punish` with a kick-category template |

Warns are per-backend (history-only, no runtime state to sync). A warn issued on `smp1` is visible from any other node via `/warns` and `/history` because it's in the shared DB, but there's no live event to react to.

## Troubleshooting

**"My ban takes 3 seconds to disconnect on the proxy."**
Enable Redis in `config/database.yml`. Without Redis, `wait-for-proxy: true` waits for the proxy to write four DB rows and reply. With Redis, the proxy disconnects the target within milliseconds.

**"My bans aren't propagating between servers."**
Check every node points at the same database (same `type` + same host + same database name). Then check `staffcore.server-id` is unique on every node; two nodes with the same id will filter each other's events out with the origin filter.

**"The proxy refuses to start."**
The proxy refuses to boot with `database.type` empty on purpose (there is no accidental "it connected to something" behaviour). Set it to `mysql` or `mongodb` and provide real credentials.

**"`/staffcore push` says 'requires Redis'."**
It does. Enable Redis in `config/database.yml`.

**"A node keeps timing out on Redis."**
Check `redis.timeout-ms`. Default is 2000. On a slow network you may need to raise it. Never set it to 0 (means "block forever").
