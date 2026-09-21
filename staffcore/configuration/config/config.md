# `config/config.yml`

Location: `plugins/StaffCore/config/config.yml`

Network-wide settings: identity of this node and how the plugin participates
in cross-server behaviour. Feature-specific settings live in
[`punishments/config.yml`](../punishments/config.md).

```yaml
staffcore:
  debug: false
  server-id: ""

cross-server:
  enabled: true
  poll-interval-seconds: 5

proxy:
  enabled: false
  wait-for-proxy: true
  timeout-ms: 2000
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `staffcore.debug` | `false` | Verbose logging for diagnostics. |
| `staffcore.server-id` | `""` (empty) | Unique identifier for THIS node inside the network. Required whenever cross-server or Redis is enabled. Used as the origin stamp on every event, the node-discovery heartbeat key, and the human-readable tag in logs. If left empty the plugin logs a WARNING and falls back to a per-boot random UUID. |
| `cross-server.enabled` | `true` | Poll the shared database for events written by other nodes and apply them locally. Only works if the database is actually shared (mysql or mongodb). |
| `cross-server.poll-interval-seconds` | `5` | How often the poller runs. When Redis is on, this is only a safety net; events arrive via Redis within milliseconds. |
| `proxy.enabled` | `false` | Delegate `/ban`, `/unban` and `/kick` to the Velocity proxy for edge-enforcement. Requires the staffcore proxy JAR to be installed on Velocity. |
| `proxy.wait-for-proxy` | `true` | Block the command until the proxy ACKs. Cleaner semantics; the staff member sees success only when the proxy has actually done the work. |
| `proxy.timeout-ms` | `2000` | Fall back to a direct DB write / local kick if the proxy is silent for this long. |

## Proxy edition

On a Velocity proxy the same file lives at
`plugins/staffcoreproxy/config/config.yml`. The proxy uses a top-level
`server-id: ...` (no `staffcore.` prefix). The `proxy:` block is ignored on
the proxy side.

## See also

- [Cross-server & Proxy](../../cross-server.md) for the full multi-node setup guide.
