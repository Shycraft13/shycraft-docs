# `config/database.yml`

Location: `plugins/StaffCore/config/database.yml`

Selects the primary database backend and configures the optional Redis
event bus.

```yaml
type: sqlite

sqlite:
  file: "staffcore.db"

mysql:
  host: localhost
  port: 3306
  database: staffcore
  username: root
  password: ""
  pool-size: 10

mongodb:
  uri: "mongodb://localhost:27017"
  database: "staffcore"

redis:
  enabled: false
  host: localhost
  port: 6379
  password: ""
  database: 0
  channel-prefix: "staffcore"
  timeout-ms: 2000
```

## Keys

### `type`

One of `sqlite`, `mysql`, `mongodb`. Only the matching block below is read.

- `sqlite` file-based, no setup, single-server only. Cross-server bans need
  `mysql` or `mongodb`.
- `mysql` covers MySQL 8.0+ and MariaDB 10.6+. Multi-server safe.
- `mongodb` MongoDB 5.0+. Multi-server safe.

### `sqlite:`

| Key | Description |
| --- | --- |
| `file` | Path to the database file, relative to `plugins/StaffCore/`. |

### `mysql:`

| Key | Description |
| --- | --- |
| `host` | Server hostname or IP. |
| `port` | Server port. |
| `database` | Database name. Must exist beforehand; tables are created automatically. |
| `username` | User with full privileges on `database`. |
| `password` | Password. |
| `pool-size` | Maximum number of connections in the pool. 2–20 is a safe range. |

### `mongodb:`

| Key | Description |
| --- | --- |
| `uri` | Any valid MongoDB connection URI. Supports replica sets and Atlas. |
| `database` | Database name inside the MongoDB instance. |

### `redis:`

Redis sits BESIDE the primary database. The primary DB stays the source of
truth; Redis is only a wake-up signal so nodes react within milliseconds
instead of waiting for the next poll tick.

| Key | Default | Description |
| --- | --- | --- |
| `enabled` | `false` | Turn Redis on. |
| `host` | `localhost` | Redis host. |
| `port` | `6379` | Redis port. |
| `password` | `""` | Empty disables auth. Set if your Redis has `requirepass`. |
| `database` | `0` | Redis database index (0..15). Keep separate from other services if you share a Redis instance. |
| `channel-prefix` | `"staffcore"` | Prefix for every channel/key so multiple staffcore networks can share a Redis instance. Every node in the same network must use the same prefix. |
| `timeout-ms` | `2000` | Socket + connect timeout. Never set to 0 (means "block forever"). |

## Proxy edition

The proxy reads the same file layout at `plugins/staffcoreproxy/config/database.yml`.
The proxy refuses to boot until `type` is set to `mysql` or `mongodb` (SQLite
is not supported on the proxy side).

## See also

- [Cross-server & Proxy](../../cross-server.md) for the full multi-node setup guide.
