# Configuration

All configuration lives under `plugins/EconomyCore/`. The plugin ships with a large set of YAML files organised by feature, so you can enable, disable and tune each subsystem in isolation.

This section reproduces every shipped default so you can:

- see what a fresh install looks like,
- diff your local file against the shipped default after an update,
- copy a default back if you break something.

## File layout

```
plugins/EconomyCore/
├── config/
│   ├── config.yml            # master feature flags + world display names
│   ├── database.yml          # database backend selection
│   ├── permission.yml        # reference of every permission node
│   └── placeholder.yml       # reference of every PlaceholderAPI placeholder
└── economy/
    ├── afk/
    ├── announcement/
    ├── bounty/
    ├── chat/
    ├── combat/
    ├── homes/
    ├── keyall/
    ├── kits/
    ├── leaderboard/
    ├── menus/
    ├── mythictools/
    ├── pay/
    ├── rtp/
    ├── rtpqueue/
    ├── rtpzone/
    ├── sell/
    ├── sellmulti/
    ├── settings/
    ├── shop/
    ├── spawn/
    ├── stats/
    ├── tags/
    ├── team/
    ├── tpa/
    ├── util/
    └── worth/
```

Each feature folder usually contains:

- `config.yml` — feature settings (numbers, toggles).
- `messages.yml` — every user-facing string, colour-coded.
- `sounds.yml` — sound event bindings.
- `gui/*.yml` — menu layouts, slot positions, item materials.

## Reload

`/economy reload` reloads every config file at runtime. Feature flags in the master `config.yml` are re-evaluated, so turning a subsystem off during a reload fully unregisters it (commands, listeners, menus, everything).
