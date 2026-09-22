# Commands

Every command is grouped by feature below. Aliases match the shipped `plugin.yml`. Permission nodes are documented in [Permissions](permissions.md).

## Bans

| Command | Aliases | Description |
| --- | --- | --- |
| `/ban <player> [time] [reason] [--kill]` |  | Ban a player. No time = permanent. Time formats: `5s`, `10m`, `2h`, `1d`, `1w`, `permanent`. `--kill` kills the target on the spot before the disconnect (so death drops trigger and stats count); flag position inside the reason doesn't matter, it is stripped from the recorded reason. |
| `/unban <player> [--void]` | `/pardon` | Remove an active ban. `--void` also voids the newest matching template-usage row so the template ladder tier does not advance because of this ban. Use when the ban was applied in error. |

## Mutes

| Command | Aliases | Description |
| --- | --- | --- |
| `/mute <player> [time] [reason]` |  | Mute chat, blocked commands, signs, books and anvil renames. If Simple Voice Chat is installed, the microphone is muted too. No time = permanent. |
| `/unmute <player>` |  | Remove an active mute. |

Which commands and text channels are blocked while a player is muted is configurable in [`punishments/config.yml`](configuration/punishments/config.md) under `mute:`.

## Warns

| Command | Aliases | Description |
| --- | --- | --- |
| `/warn <player> [reason]` |  | Add a warn to the player's history. The warn count is displayed and drives template ladders. |
| `/unwarn <player> <id> [--void]` |  | Remove a warn by its short id (6 hex chars, visible in `/warns`). `--void` keeps the row in history but voids it so it no longer counts toward template ladder progression. |
| `/warns <player>` | `/warnings` | Print the player's warn history to chat. |

## Kicks

| Command | Description |
| --- | --- |
| `/kick <player> [reason]` | Kick a player. Recorded in history like any other punishment. |

## Templates

| Command | Description |
| --- | --- |
| `/punish <player>` | Open the punish GUI: shows every template you have permission to use, colour-coded per category (ban / mute / warn / kick). |
| `/punish <player> <template> [--kill]` | Apply the named template directly. Template category determines the action. `--kill` only affects BAN-category templates, mirrors `/ban --kill`. |

Templates are defined in [`punishments/punishments.yml`](configuration/punishments/punishments.md). See [Punishment Templates](templates.md) for the ladder model.

## History & alts

| Command | Description |
| --- | --- |
| `/history <player>` | Open the `/history` GUI: paginated list of every ban, mute, warn, kick for the target. Filter by type, sort newest-first / oldest-first. Each entry shows whether it is still active, expired naturally, or was manually lifted. |
| `/alts <player>` | Open the `/alts` GUI: every account that has shared an IP with the target, colour-coded online / offline / banned. IPs themselves are never shown in-game (only counted). Query the database directly if you need the raw addresses. |

## Teleports

Registered when `features.teleports: true` in
[`config/config.yml`](configuration/config/config.md). Per-command
permissions live in [Permissions](permissions.md#teleports); the shared
settings (safe-teleport, back-stack size, blocked worlds, cross-server
switch) live in [`teleports/config.yml`](configuration/teleports/config.md).

| Command | Description |
| --- | --- |
| `/tp <player>` | Teleport to a player. Same-server = live position. Cross-server (with `teleports.cross-server: true` + proxy) = you are transferred to the target's server and land at their location. Offline targets teleport to their last logout position (requires `staffcore.tp.offline`). |
| `/tphere <player>` | Pull an online player to your location. Cross-server aware. The target sees a `target-notify` message. Immunity via `staffcore.tp.bypass`. Offline targets are rejected. |
| `/tppos <x> <y> <z> [world] [server]` | Teleport to explicit coordinates. `[world]` defaults to your current world. `[server]` triggers a cross-server transfer to that server id. |
| `/back` | Return to your previous location. Every `/tp`, `/tphere`, `/tppos` and cross-server transfer pushes onto the back-stack; `/back` pops one. Back-stack size and cross-server behaviour live in [`teleports/config.yml`](configuration/teleports/config.md). |

## Admin

| Command | Aliases | Description |
| --- | --- | --- |
| `/staffcore reload` | `/sc reload` | Re-read every YAML under `plugins/StaffCore/`. Templates + message cache rebuild. Database pool + registered listeners are not restarted. |
| `/staffcore push` | `/sc push` | Open the config-push GUI: pick source node, pick target servers, pick a preset, confirm. Every matching node rewrites its config tree and soft-reloads. Requires Redis. |
| `/staffcore push <from> <to\|*> <preset>` | `/sc push ...` | Scripted mode. `<from>` names the source node (any live node, not necessarily the current one); `<to>` is a receiver or `*` for every node except `<from>`. Preset is one of `punishments`, `database`, `gui`, `all`. When run by a player, opens the [confirm GUI](configuration/push/confirm.md) so a chat typo can't push by accident. Append `--yes` (alias `-y`) to skip the confirm, required in shell scripts. `config/config.yml` is never pushed (holds per-node identity). When `<from>` is not the current node, the request is forwarded via Redis and the named source publishes. See [Cross-server & Proxy](cross-server.md#config-push). |
| `/staffcore update` | `/sc update` | Open the JAR-update GUI: pick source node, pick target servers, confirm. Every matching node stages the new JAR in `plugins/update/` and swaps it in on the next server restart. Requires Redis. |
| `/staffcore update <from> <to\|*>` | `/sc update ...` | Scripted mode. `<from>` names the source node whose JAR gets shipped (any live node); `<to>` is a receiver or `*` for every node except `<from>`. When run by a player, opens the [confirm GUI](configuration/update/confirm.md) so a chat typo can't ship a JAR by accident. Append `--yes` (alias `-y`) to skip the confirm, required in shell scripts. Missing config files the new JAR ships get recreated on the receiver's first enable after the swap. When `<from>` is not the current node, the request is forwarded via Redis and the named source publishes. See [Cross-server & Proxy](cross-server.md#jar-update). |

## Time format

Every command that accepts a `time` argument uses the same parser:

| Format | Meaning |
| --- | --- |
| `30s` | 30 seconds |
| `10m` | 10 minutes |
| `2h` | 2 hours |
| `1d` | 1 day |
| `1w` | 1 week |
| `permanent` (or omit) | Permanent |

Combined values like `1d12h` are also supported.

## Broadcasts

Every ban, unban, mute, unmute, warn and kick broadcast fires to everyone with `staffcore.notify`. The banned / muted / kicked target itself is filtered out of the broadcast. Console can be included or excluded via `punishments.broadcast-to-console` in [`punishments/config.yml`](configuration/punishments/config.md).

## Tab completion

Every command that takes a player argument tab-completes across the whole network when cross-server is enabled: online players on any backend or proxy appear in the suggestions, not just the local server.
