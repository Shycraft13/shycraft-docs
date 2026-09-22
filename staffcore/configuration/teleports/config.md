# `teleports/config.yml`

Location: `plugins/StaffCore/teleports/config.yml`

Settings for the teleport feature (`/tp`, `/tphere`, `/tppos`, `/back`). The
whole feature is gated by `features.teleports` in `config/config.yml`; when
that toggle is off, everything below is ignored and no teleport command is
registered.

```yaml
teleports:
  cross-server: false
  track-last-location: true
  safe-teleport: true
  back-stack-size: 5
  pending-teleport-ttl-seconds: 60
  blocked-worlds: []
```

## Options

| Key | Default | Purpose |
| --- | --- | --- |
| `cross-server` | `false` | Per-feature switch on top of the network-wide `cross-server.enabled`. When **off**, `/tp`, `/tphere`, `/tppos` only work against players on **this** server; offline targets and other-server targets are rejected. When **on** (and `cross-server.enabled: true` and `proxy.enabled: true`), the sender is transferred through the proxy and lands at the target's location. |
| `track-last-location` | `true` | If on, the server keeps a small "last seen" snapshot per player. Powers `/tp <offline-player>` (last logout position) and cross-server `/tp` against online players on other backends. Off disables both and skips the periodic snapshot. |
| `safe-teleport` | `true` | When on, refuses to teleport into unsafe blocks (lava, magma, fire, campfires, blocks with no floor). Bumps up to 5 blocks looking for a safe spot; if none is found the teleport is cancelled with a "no safe location" action bar. Off teleports the player exactly to the requested coordinates, no matter what. |
| `back-stack-size` | `5` | How many previous locations `/back` remembers per player. Higher = further undo, more storage rows. `/back` never records itself, so a ping-pong doesn't grow the stack. |
| `pending-teleport-ttl-seconds` | `60` | Timeout for a cross-server teleport. If the target server doesn't pick the arriving player up within this window (proxy transfer failed, target down), the pending teleport is dropped. Once the client actually arrives and the server teleports them, the row is consumed regardless of TTL. |
| `blocked-worlds` | `[]` | List of world names staff cannot teleport into. Case-insensitive. Bypass via `staffcore.teleport.admin`. Use for world-borders, private staff areas, or in-progress builds. |

## Commands + permissions

| Command | Permission | Notes |
| --- | --- | --- |
| `/tp <player>` | `staffcore.tp` | Add `staffcore.tp.offline` for last-logout teleport. |
| `/tphere <player>` | `staffcore.tphere` | Target-side immunity: `staffcore.tp.bypass`. |
| `/tppos <x> <y> <z> [world] [server]` | `staffcore.tppos` | `[server]` requires `cross-server: true`. |
| `/back` | `staffcore.back` |  |

## Message keys

Chat + action-bar templates live in `teleports/messages.yml` so they can be
translated / restyled without touching feature behavior. Placeholders:
`%player%`, `%sender%`, `%server%`, `%world%`, `%x% %y% %z%`.
