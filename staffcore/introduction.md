# Introduction

**staffcore** is a full staff and moderation toolkit for Paper-based Minecraft servers. It ships every day-to-day moderation command your staff needs, plus a LiteBans-style template system with automatic tier progression and cross-server synchronisation.

## What's inside

- **Bans** permanent, temporary or via template. Ban screens are fully configurable.
- **Mutes** chat, commands, signs, books, anvil renames, and Simple Voice Chat microphone all blocked from a single mute record.
- **Warns** with a per-player history and a numeric ladder threshold that can drive escalating actions.
- **Kicks** persistent history entries just like bans and mutes.
- **Punishment templates** LiteBans-style presets (e.g. `cheating`, `spam`, `advertising`), each with a tier ladder that escalates automatically on repeat offences. Templates fully replace the "should this be a 3d ban or a 7d ban?" guesswork.
- **`/punish` GUI** picker menu that shows every template, per-category colour, current tier hint, and click-to-apply.
- **`/history` GUI** paginated timeline of every ban, mute, warn and kick a player ever received. Filter by type, sort newest/oldest, each entry shows lifted / expired / still-active status.
- **`/alts` GUI** every account that has ever shared an IP address with the target, colour-coded by online / offline / banned status. IPs themselves are never rendered in-game.
- **Cross-server** every ban, unban, mute, unmute and kick automatically propagates to every backend and the proxy sharing the same database, with an optional Redis event bus for sub-second latency.
- **Config push** `/staffcore push` copies your `punishments/` folder to every other node in one command. No more editing the same YAML on five backends.
- **Multi-backend storage** MongoDB, MySQL/MariaDB, and SQLite are all first-class.

## Design goals

- **One JAR, both platforms.** The same artifact runs on Paper backends and on a Velocity proxy. Descriptors for both platforms coexist inside the JAR; each side loads only what it needs.
- **YAML-only customisation.** Every command, message, screen, sound, GUI title, GUI slot and colour is in a config file. No recompile required.
- **Redis-optional.** Redis makes cross-server ban propagation real-time. Turn it off and the plugin falls back to a poll-based path with the same guarantees, just with a few seconds of latency.
- **LiteBans-compatible template model.** Anyone who knows LiteBans templates can pick up staffcore's `punishments.yml` immediately; the differences are documented in [Punishment Templates](templates.md).

## Version compatibility

- **Minecraft**: 1.21+
- **Server software**: Paper (and Paper forks) for backends, Velocity for the proxy
- **Java**: 21
- **Database**: MongoDB 5.0+, MySQL 8.0+ / MariaDB 10.6+, or SQLite (bundled)
- **Redis**: 6.0+ (optional, only needed for real-time cross-server events and `/staffcore push`)
