# Database (`config/database.yml`)

Selects the database backend. Three backends are supported and can be switched by changing `type`.

Location: `plugins/EconomyCore/config/database.yml`

```yaml
# Database backend to use.
# Options: sqlite  |  mysql  |  mongodb
type: sqlite

# ─── SQLite ────────────────────────────────────────────────────────────────
# Lightweight file-based database. Perfect for single-server setups.
sqlite:
  # Path to the database file, relative to the plugin data folder.
  file: "database.db"

# ─── MySQL / MariaDB ───────────────────────────────────────────────────────
# Use for multi-server setups or when you need remote access to the data.
mysql:
  host: localhost
  port: 3306
  database: economysmp
  username: root
  password: ""
  # Maximum number of connections in the pool (2–20 recommended).
  pool-size: 10

# ─── MongoDB ───────────────────────────────────────────────────────────────
# Original backend. Keep this block if you are migrating from MongoDB.
mongodb:
  uri: "mongodb://localhost:27017"
  name: "economysmp"
```

## Which one should I pick?

| Backend | Use case |
| --- | --- |
| **SQLite** | Single server, no external DB. Zero setup. Best default. |
| **MySQL / MariaDB** | Multiple servers sharing the same economy, or you want remote access to the data. |
| **MongoDB** | You already run a MongoDB cluster, or you are migrating from an earlier setup. |

Tables/collections are created automatically on first start; no manual schema setup is required.
