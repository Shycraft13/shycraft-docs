# Configuration

This section reproduces every YAML file shipped with economy-core, laid out
in the exact folder structure they have under `plugins/EconomyCore/`.

Each page shows one file so you can diff your local copy against the shipped
default after an update. Comments are stripped: the pages show only the
actual key/value structure you need to edit.

Two top-level roots:

- `config/` — cross-cutting configs: master `config.yml`, database, permission
  and placeholder reference.
- `economy/` — one folder per feature. Each folder holds `config.yml`,
  `messages.yml`, `sounds.yml` and any `gui/*.yml` files that feature uses.

Use `/economy reload` to reload every file at runtime.
