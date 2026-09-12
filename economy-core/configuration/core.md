# Core (`config/config.yml`)

The master configuration file. Controls the starting balance, world display names, debug mode, and the master feature-flag block that toggles every subsystem.

Location: `plugins/EconomyCore/config/config.yml`

```yaml
economy:
  starting-balance: 1000.0

# Custom display names for worlds, used by the %world% placeholder.
# Any world not listed here shows its raw name.
world-names:
  world: "overworld"
  world_nether: "nether"
  world_the_end: "end"

# Only enable if you know what you are doing.
debug: false

features:
  pay: true
  homes: true
  tpa: true
  rtp: true
  sell: true
  worth: true
  shop: true
  statistics: true
  leaderboard: true
  bounty: true
  team: true
  keyall: true
  chat: true
  spawn: true
  afk: true
  rtpzone: true
  rtpqueue: true
  announcement: true
  menus: true
  kits: true
  tags: true
  util: true
```

## Notes

- **`starting-balance`** — money every player has the first time they join.
- **`world-names`** — display aliases used by placeholders and command tab-completion. `/rtp nether` works because `nether` is the alias for `world_nether`.
- **`debug`** — enables verbose logging and unlocks internal debug commands. Leave off in production.
- **`features.*`** — set any feature to `false` to fully disable it. Its commands are unregistered, its listeners removed, its GUIs shut down. No leftovers.
