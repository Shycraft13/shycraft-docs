# Introduction

**economy-core** is an all-in-one core plugin built for the Shycraft SMP network. It bundles the systems most survival servers stitch together from many small plugins into one cohesive, performance-focused package.

## What's inside

- **Economy** — Vault-compatible balance system with `/pay`, `/balance`, leaderboards and admin management commands.
- **Shards** — a secondary "premium" currency separate from money, used for shop rewards and kill bounties.
- **Homes** — per-player named homes with configurable limits and cooldowns.
- **Teleportation** — `/tpa`, `/tpahere`, `/back`, and `/rtp` with configurable world zones.
- **Teams** — full team system with roles, permissions, shared home and PvP toggle.
- **Bounties** — put money on players' heads; killers claim automatically.
- **Kits** — configurable kits with cooldowns, exact-slot inventory layouts and an in-game editor.
- **Chat** — global chat routing, mention pings, ignore lists, first-join welcome message.
- **Utility commands** — `/enderchest`, `/craft`, `/anvil`, `/grindstone`, `/loom`, `/cartography`, `/smithing`, `/stonecutter`, `/glow`.
- **Leaderboards** — packet-based, no-inventory GUIs for balance, kills, bounties and playtime.

## Design goals

- **One plugin, no dependencies.** Every feature above lives inside a single JAR. No BentoBox, no Essentials, no CMI.
- **Runs on Folia forks.** Every scheduled task uses region-aware scheduling. Tested on Canvas.
- **NMS packet GUIs.** All interactive menus (shop, kits, worth, leaderboards, teams, bounties) are packet-based and structurally dupe-proof.
- **Backend of your choice.** MongoDB, MySQL/MariaDB and SQLite are all first-class.

## Version compatibility

- **Minecraft**: 1.21+
- **Server software**: Paper, Purpur, Folia, Canvas
- **Java**: 21
