# Installation

## Requirements

- **Server software**: Paper 1.21 or newer, or a Paper fork
- **Java**: 21 or newer
- **Database**: one of the following
  - MongoDB 5.0+
  - MySQL 8.0+ / MariaDB 10.6+
  - SQLite (bundled, no setup required)

## Steps

1. Stop your server.
2. Drop `EconomyCore-<version>.jar` into your `plugins/` directory.
3. Start the server once so the default config files are generated under `plugins/EconomyCore/`.
4. Stop the server, edit `plugins/EconomyCore/config/database.yml` to pick your backend (see below).
5. Start the server again.

## Database configuration

`plugins/EconomyCore/config/database.yml` controls which backend is used.

### SQLite (default, zero setup)

```yaml
type: sqlite
sqlite:
  file: data/economy.db
```

Nothing else to configure. The database file is created on first start.

### MySQL / MariaDB

```yaml
type: mysql
mysql:
  host: 127.0.0.1
  port: 3306
  database: economysmp
  username: economy
  password: change_me
  pool-size: 10
```

Create the database and user yourself before starting:

```sql
CREATE DATABASE economysmp CHARACTER SET utf8mb4;
CREATE USER 'economy'@'%' IDENTIFIED BY 'change_me';
GRANT ALL PRIVILEGES ON economysmp.* TO 'economy'@'%';
FLUSH PRIVILEGES;
```

Tables are created automatically on first start.

### MongoDB

```yaml
type: mongodb
mongodb:
  uri: mongodb://economy:change_me@127.0.0.1:27017
  database: economysmp
```

Any valid MongoDB connection URI works, including replica sets and Atlas.

## Verification

After startup you should see a line like:

```
[EconomyCore] Connected to SQLite successfully.
```

(or `MySQL/MariaDB` / `MongoDB` depending on your choice).

If the plugin fails to connect it disables itself with a clear error in the console. Fix the credentials or connectivity issue and start the server again.
