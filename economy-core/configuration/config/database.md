# `config/database.yml`

Location: `plugins/EconomyCore/config/database.yml`

```yaml

type: sqlite

sqlite:

  file: "database.db"

mysql:
  host: localhost
  port: 3306
  database: economysmp
  username: root
  password: ""

  pool-size: 10

mongodb:
  uri: "mongodb://localhost:27017"
  name: "economysmp"
```
