# Configuration

All configuration lives under `plugins/EconomyCore/config/`. Each feature has its own file so you can disable, tune, or reload individual systems without touching the rest.

## File layout

```
plugins/EconomyCore/
├── config/
│   ├── config.yml              # master config, feature flags, world names
│   ├── database.yml            # database backend
│   ├── messages.yml            # every user-facing message
│   ├── sounds.yml              # every sound played by the plugin
│   └── ...                     # per-feature configs (see below)
└── data/                       # runtime data (SQLite file, etc.)
```

## The master config: `config.yml`

The top-level `config.yml` controls which subsystems are active. Every feature can be turned off individually.

```yaml
features:
  economy: true
  homes: true
  tpa: true
  rtp: true
  teams: true
  bounty: true
  kits: true
  chat: true
  util: true
  shards: true
  leaderboard: true
```

Setting any of these to `false` fully unregisters the corresponding commands, listeners and GUIs. No leftover state, no orphan tab-completions.

## World display names

Many commands accept world names both by their internal ID (`world_nether`, `world_the_end`) and by a friendlier display name defined once here:

```yaml
world-names:
  world: "Overworld"
  world_nether: "Nether"
  world_the_end: "End"
```

For example `/rtp nether` works because `Nether` is the configured display name for `world_nether`.

## Per-feature configs

Each subsystem has its own file. The files are self-documenting: every key has a comment explaining what it does and what the default is.

| File | Feature |
| --- | --- |
| `economy/config.yml` | Balances, `/pay` cooldowns, leaderboard settings |
| `shards/config.yml` | Shard currency, kill rewards, per-victim cooldown |
| `homes/config.yml` | Per-permission home limits, teleport delays |
| `tpa/config.yml` | Request timeouts, teleport delays |
| `rtp/config.yml` | Per-world zones, cooldowns, safe-teleport search |
| `team/config.yml` | Team size limits, home-set cost, PvP defaults |
| `bounty/config.yml` | Bounty minimums and taxes |
| `kits/config.yml` | Kit definitions, per-kit cooldowns |
| `chat/config.yml` | Chat format, mention regex, ignore behaviour |
| `util/config.yml` | Which utility commands are enabled, `/glow` settings |
| `menus/*.yml` | Custom menu definitions (buttons, items, actions) |

## Reload

`/economycore reload` reloads all configs and messages without restarting the server. Feature flags are re-evaluated: a subsystem turned off in the config is fully unregistered on the fly.
