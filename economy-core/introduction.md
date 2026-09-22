# Introduction

**economy-core** is an all-in-one core plugin built for the Shycraft SMP network. It bundles the systems most survival servers stitch together from many small plugins into one cohesive package.

## What's inside

- **Economy** — Vault-compatible balance system with `/pay`, `/balance`, leaderboards and admin management commands.
- **Shards** — a secondary currency separate from money, used for shop rewards and kill bounties.
- **Homes** — per-player named homes with configurable limits and cooldowns.
- **Teleportation** — `/tpa`, `/tpahere`, `/back`, and `/rtp` with configurable world zones.
- **Teams** — full team system with roles, permissions, shared home and PvP toggle.
- **Bounties** — put money on players' heads; killers claim automatically.
- **Kits** — configurable kits with cooldowns and an in-game editor.
- **Chat** — global chat routing, mention pings, ignore lists, first-join welcome message.
- **Utility commands** — `/enderchest`, `/craft`, `/anvil`, `/grindstone`, `/loom`, `/cartography`, `/smithing`, `/stonecutter`, `/glow`.
- **Leaderboards** — balance, kills, bounties and playtime, all with clean menus.
- **Shop, Sell, Worth** — configurable shop menus, item selling, worth lookup.
- **Spawn, Tags, Stats, Settings** — quality-of-life systems every SMP eventually wants.

## Design goals

- **One plugin, no dependencies.** Every feature above lives inside a single JAR.
- **Backend of your choice.** MongoDB, MySQL/MariaDB and SQLite are all first-class.
- **Every feature can be turned off individually.** The master `config.yml` has a feature-flag per subsystem.

## Version compatibility

- **Minecraft**: 1.21+
- **Server software**: Paper and Paper forks
- **Java**: 21
