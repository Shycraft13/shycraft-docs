# Installation

## Requirements

- **Server software**: Paper 1.21 or newer (or a Paper fork) for backends. Velocity 3.3+ for the proxy.
- **Java**: 21 or newer.
- **Database**: one of the following.
  - SQLite (bundled, zero setup). Single-server only.
  - MySQL 8.0+ / MariaDB 10.6+ (recommended for multi-server).
  - MongoDB 5.0+ (recommended for multi-server).
- **Redis 6.0+**: optional, needed only for real-time cross-server events and `/staffcore push`.
- **PacketEvents plugin**: required dependency on backends. Grab the latest release from Modrinth or SpigotMC and drop it into `plugins/`.
- **Simple Voice Chat**: optional. If present, staffcore's mute record also blocks the muted player's microphone.

## Backend setup (Paper)

1. Stop your server.
2. Drop `PacketEvents-<version>.jar` and `StaffCore-<version>.jar` into `plugins/`.
3. Start the server once so the defaults are written to `plugins/StaffCore/`.
4. Stop the server and edit `plugins/StaffCore/config/database.yml` (see below).
5. If you run multiple servers or a proxy, edit `plugins/StaffCore/config/config.yml` and set a unique `staffcore.server-id` (e.g. `smp1`).
6. Start the server again.

## Proxy setup (Velocity, optional)

Only needed if you want ban/unban/kick decisions enforced at the proxy edge (recommended for multi-backend networks).

1. Stop your proxy.
2. Drop the **same** `StaffCore-<version>.jar` into `plugins/` on the proxy. The JAR is universal.
3. Start the proxy once so `plugins/staffcoreproxy/` is generated.
4. Stop the proxy, edit `plugins/staffcoreproxy/config/database.yml` and set the SAME `type` + credentials as your backends (proxy needs to talk to the same shared DB).
5. Edit `plugins/staffcoreproxy/config/config.yml` and give the proxy its own `server-id` (e.g. `proxy-a`).
6. On each backend, edit `plugins/StaffCore/config/config.yml` and set:
   ```yaml
   proxy:
     enabled: true
     wait-for-proxy: true
   ```
7. Start the proxy, then your backends.

The proxy refuses to start until `database.type` is set. SQLite is **not** valid for the proxy on purpose (each side would have its own file). Use `mysql` or `mongodb`.

## Database configuration

`plugins/StaffCore/config/database.yml` controls which backend is used.

### SQLite (default, zero setup)

```yaml
type: sqlite
sqlite:
  file: "staffcore.db"
```

Nothing else to configure. The database file is created on first start. Not usable for multi-server networks.

### MySQL / MariaDB

```yaml
type: mysql
mysql:
  host: 127.0.0.1
  port: 3306
  database: staffcore
  username: staffcore
  password: change_me
  pool-size: 10
```

Create the database and user yourself before starting:

```sql
CREATE DATABASE staffcore CHARACTER SET utf8mb4;
CREATE USER 'staffcore'@'%' IDENTIFIED BY 'change_me';
GRANT ALL PRIVILEGES ON staffcore.* TO 'staffcore'@'%';
FLUSH PRIVILEGES;
```

Tables are created automatically on first backend start. Proxy connects to the same tables afterwards.

### MongoDB

```yaml
type: mongodb
mongodb:
  uri: "mongodb://staffcore:change_me@127.0.0.1:27017"
  database: "staffcore"
```

Any valid MongoDB connection URI works, including replica sets and Atlas.

## Redis (optional, real-time cross-server)

Same `config/database.yml`, `redis:` block:

```yaml
redis:
  enabled: true
  host: 127.0.0.1
  port: 6379
  password: ""
  database: 0
  channel-prefix: "staffcore"
  timeout-ms: 2000
```

When enabled, every backend and proxy sharing the same Redis instance sees ban / unban / mute / unmute / kick events within milliseconds. Without Redis the plugin falls back to a database poller that runs every 5 seconds; nothing is lost, but the network takes up to 5 seconds to catch up. See [Cross-server & Proxy](cross-server.md) for the full picture.

Keep Redis on a private network. TLS is not wired up here.

## Verification

After startup you should see lines like:

```
[StaffCore] Connected to SQLite successfully.
[StaffCore] Loaded 8 templates (3 ban, 3 mute, 1 warn, 1 kick).
[StaffCore] Registered 32 permission node(s) from permissions.yml.
```

If Redis is enabled you should additionally see:

```
[StaffCore] Redis connected (staffcore:events, heartbeat 10s).
[StaffCore] Redis subscriber ready.
```

If the plugin fails to connect to the primary DB, it disables itself with a clear error in the console. Fix the credentials or connectivity and start the server again.

## First-run checklist

- Server-id is set on every node (`staffcore.server-id` for backends, `server-id` on the proxy).
- Every node in the network points at the **same** MySQL or MongoDB instance.
- If you use Redis, all nodes share the same Redis + same `channel-prefix`.
- Backend `proxy.enabled` is `true` only if you actually deployed the proxy JAR.
- Staff have the base `staffcore.use` permission plus the specific `staffcore.ban`, `staffcore.mute`, ... they need. See [Permissions](permissions.md).
