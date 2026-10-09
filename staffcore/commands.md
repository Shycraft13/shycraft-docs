# Commands

Every command is grouped by feature below. Aliases match the shipped `plugin.yml`. Permission nodes are documented in [Permissions](permissions.md).

**Players who never joined.** Punishment commands (`/ban`, `/mute`, `/warn`, `/punish`, `/history`, `/alts`) and the maintenance bypass list also accept players who have never been on your server: the name is looked up as a Minecraft account. A name that does not belong to a real account is refused with "Player not found", so a typo never bans or whitelists a player who does not exist. `/kick`, `/freeze`, `/vanish` and `/spy` only work on players who are or were online.

## Bans

| Command | Aliases | Description |
| --- | --- | --- |
| `/ban <player> [time] [reason] [--kill] [--ip]` |  | Ban a player with your own reason (templates are applied with `/punish`). No time = permanent. The time can stand anywhere: `/ban Steve hacking 7d`, `/ban Steve 1d 12h spam`, `/ban Steve griefing 7 days`. Time formats: `5s`, `10m`, `2h`, `1d`, `1w`, `permanent` (`permanent` only as the first word after the name). `--kill` kills the target on the spot before the disconnect (so death drops trigger and stats count). `--ip` also bans every IP the player was seen on: other accounts already online from those IPs are kicked with the same ban screen, and no other account can join from them until the ban ends or `/unban` lifts it (needs `staffcore.ban.ip`). Flag position inside the reason does not matter, flags are stripped from the recorded reason. |
| `/unban <player> [--void]` | `/pardon` | Remove an active ban. `--void` also voids the newest matching template-usage row so the template ladder tier does not advance because of this ban. Use when the ban was applied in error. Scope permissions: `staffcore.unban` for any ban, `staffcore.unban.group` for bans issued by staff in your own or a weaker `limits.yml` group, `staffcore.unban.own` for bans you issued yourself. |
| `/checkban <player \| #id>` |  | Chat summary of a ban. Pass a player name for their active ban, or `#<id>` (the ban id shown on the disconnect screen) to look up ANY ban including expired / manually lifted ones. |

## Mutes

| Command | Aliases | Description |
| --- | --- | --- |
| `/mute <player> [time] [reason] [--ip]` |  | Mute chat, blocked commands, signs, books and anvil renames. If Simple Voice Chat is installed, the microphone is muted too. No time = permanent. The time can stand anywhere, for example `/mute Steve spam 7d`. Templates are applied with `/punish`. `--ip` also mutes every account that is online or joins from an IP the player was seen on, on every server, until the mute ends or `/unmute` lifts it (needs `staffcore.mute.ip`). Re-muting a player who is already muted overrides the old mute; the previous entry is closed out in history and the new one takes over (same behaviour as re-banning). |
| `/unmute <player>` |  | Remove an active mute. Scope permissions: `staffcore.unmute` for any mute, `staffcore.unmute.group` for mutes issued by staff in your own or a weaker `limits.yml` group, `staffcore.unmute.own` for mutes you issued yourself. |
| `/checkmute <player>` |  | Chat summary of the target's active mute or a brief "not muted" action bar if there is none. |

Which commands and text channels are blocked while a player is muted is configurable in [`punishments/config.yml`](configuration/punishments/config.md) under `mute:`.

## Warns

| Command | Aliases | Description |
| --- | --- | --- |
| `/warn <player> [reason]` |  | Add a warn to the player's history with your own reason (templates are applied with `/punish`). The warn count is displayed and drives template ladders. |
| `/unwarn <player> <id> [--void]` |  | Remove a warn by its short id (6 hex chars, visible in `/warns`). `--void` keeps the row in history but voids it so it no longer counts toward template ladder progression. Scope permissions: `staffcore.unwarn` for any warn, `staffcore.unwarn.group` for warns issued by staff in your own or a weaker `limits.yml` group, `staffcore.unwarn.own` for warns you issued yourself. |
| `/warns <player>` | `/warnings` | Print the player's warn history to chat. |
| `/checkwarn <player>` |  | Chat summary of the target's active (non-voided) warns, header line plus the 5 most recent entries. Full history is behind `/warns`. |

## Kicks

| Command | Description |
| --- | --- |
| `/kick <player> [reason]` | Kick a player with your own reason (templates are applied with `/punish`). Recorded in history like any other punishment. |

## Inspect

| Command | Aliases | Description |
| --- | --- | --- |
| `/invsee <player>` |  | Open another player's inventory. Read-only with `staffcore.invsee.use`, editable with `staffcore.invsee.edit`. Read-only shows a display copy only: nothing can be taken out, so `staffcore.invsee.use` is safe to give to every player. Cross-server aware and works on offline targets (changes are written back on their next login or immediately when they are online). Immunity via `staffcore.inspect.bypass`. |
| `/echestsee <player>` | `/endersee`, `/enderchestsee` | Same as `/invsee` but for the target's enderchest. Read-only is a display copy as well, so `staffcore.echestsee.use` is safe to give to every player. |

## Templates

| Command | Description |
| --- | --- |
| `/punish <player>` | Open the punish GUI: shows every template you have permission to use, colour-coded per category (ban / mute / warn / kick). |
| `/punish <player> <template> [--kill] [--ip]` | Apply the named template directly. Template category determines the action. `--kill` only affects BAN-category templates, mirrors `/ban --kill`. `--ip` only affects BAN and MUTE templates, mirrors `/ban --ip` and `/mute --ip`. |

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
| `/randomtp` | Teleport to a random online player across the whole network. No arguments. The picker never lands on you, and if the picked player just went offline you get a "try again" message. Uses the same routing as `/tp` once a target is picked (same-server or cross-server transfer). |

## Refund

Registered when `features.refund: true` in
[`config/config.yml`](configuration/config/config.md). Feature settings
(retention, capture triggers, cross-server switch) live in
[`refund/config.yml`](configuration/refund/config.md).

| Command | Description |
| --- | --- |
| `/refund <player>` | Open the refund GUI for the given player. First screen picks a category (Death / Join / Quit / Enderchest), then a paginated list of snapshots, then a per-snapshot action menu (Replace / Give-Out / Teleport / View). Works for online and offline targets alike, cross-server aware. |

Per-button permissions are documented in
[Permissions](permissions.md#refund). GUI slots, materials, titles and
lore are fully customisable, see
[`refund/gui/`](configuration/refund/gui/category.md).

## Gamemodes

Registered when `features.gamemodes: true` in
[`config/config.yml`](configuration/config/config.md). Cross-server and
offline switches live in
[`gamemodes/config.yml`](configuration/gamemodes/config.md); chat
strings live in
[`gamemodes/messages.yml`](configuration/gamemodes/messages.md).

| Command | Aliases | Description |
| --- | --- | --- |
| `/gamemode <mode> [player]` | `/gm` | Change a player's gamemode. `<mode>` accepts `survival`/`s`/`0`, `creative`/`c`/`1`, `adventure`/`a`/`2`, `spectator`/`sp`/`3` (case-insensitive). Without `[player]`, changes your own gamemode. With a `[player]` argument, works cross-server (online target on another backend) and on offline targets — every backend that stores player data for that UUID converges to the new mode, so the change sticks no matter which node they log into next. |
| `/gms [player]` |  | Shortcut for survival. |
| `/gmc [player]` |  | Shortcut for creative. |
| `/gma [player]` |  | Shortcut for adventure. |
| `/gmsp [player]` |  | Shortcut for spectator. |

Per-mode permissions and the "other player" / "offline" gates are
documented in [Permissions](permissions.md#gamemodes).

## Chat control

Registered when `features.chat: true` in
[`config/config.yml`](configuration/config/config.md). Filter behaviour
lives in [`chat/config.yml`](configuration/chat/config.md); the
anti-swear list lives in
[`chat/blocked-words.yml`](configuration/chat/blocked-words.md).

| Command | Description |
| --- | --- |
| `/chat clear` | Wipe chat network-wide. Bypassed by anyone with `staffcore.chat.bypass`. |
| `/chat pause [duration]` | Pause chat network-wide, optionally for a fixed duration (`10m`, `1h`, ...). Without a duration the pause stays until `/chat unpause`. |
| `/chat unpause` | Resume chat network-wide. |

## Announcements

| Command | Description |
| --- | --- |
| `/announce <message>` | Full-render network-wide broadcast: title, chat line and sound. Colour codes and formatting from the message survive. |
| `/broadcast <message>` | Chat-only network-wide broadcast (no title, no sound). |

## Staff chat

| Command | Description |
| --- | --- |
| `/staffchat` | Toggle staff chat. While active every message you send routes to the staff channel instead of public chat. Receiving is gated by `staffcore.staffchat` as well. |

## Spy

| Command | Description |
| --- | --- |
| `/spy <player>` | Toggle spying on a target's chat, private messages (both sent and received) and executed commands. Cross-server. |
| `/spy list` | List everyone you are currently spying on. |
| `/spy clear` | Stop spying on every current target in one call. |

## Freeze

| Command | Description |
| --- | --- |
| `/freeze <player> [reason]` | Toggle freeze on a player. A frozen player cannot move, take fall damage or execute most gameplay commands. Cross-server aware and works on offline targets (the freeze applies on their next login). |

## Vanish

| Command | Aliases | Description |
| --- | --- | --- |
| `/vanish [player]` | `/v` | Toggle vanish. Hides you from non-staff, silences join / quit messages, and skips container open animations for other players. Persists in the database so it survives restarts, and follows you across servers. `[player]` requires `staffcore.vanish.other`. |

## Utils

Registered when `features.utils: true` in
[`config/config.yml`](configuration/config/config.md). Every command
below is cross-server aware; `[player]`-targeted variants work on
offline targets via a pending flag that is applied on their next login.

| Command | Description |
| --- | --- |
| `/fly [player]` | Toggle fly on yourself or another player. |
| `/flyspeed [player] <0-10\|reset>` | Set or reset fly speed (0-10). `reset` restores the vanilla default. |
| `/speed [player] <0-10\|reset>` | Set or reset walk speed (0-10). |
| `/heal [player]` | Fully heal a player (health, fire, air). |
| `/feed [player]` | Refill hunger and saturation to max. |
| `/repair [player]` | Repair the item in the target's main hand. |
| `/near [radius]` | List nearby players in your current world. Radius capped at 500. |
| `/top` | Teleport to the highest solid block above your current XZ. |

## Reports

Registered when `features.reports: true` in
[`config/config.yml`](configuration/config/config.md). Behaviour
settings (cooldowns, length caps, Discord webhook, auto-cleanup) live
in [`reports/config.yml`](configuration/reports/config.md).

| Command | Aliases | Description |
| --- | --- | --- |
| `/report <player> <message>` |  | File a report against another player. Everything after `<player>` is the report body — one field, capped by `reports.message-max-chars` (default 800) with a rejection floor of `reports.message-min-chars` (default 3). The full message renders in the staff feed, review GUI and Discord embed. Rate-limited per reporter via `reports.cooldown-seconds` (bypass with `staffcore.report.cooldown-bypass`). |
| `/report check <player>` |  | Open the per-target report list (paginated GUI, filter by status, sort by date). |
| `/report check #<report-id>` |  | Jump straight into the detail GUI for a single report. The `#` prefix disambiguates from a player name. |
| `/reports` |  | Open the network-wide paginated report list. |
| `/reports list` |  | Hidden alias of `/reports` kept for muscle memory. |

Reviewing is gated by `staffcore.reports.review`. Filing is default-TRUE, so every player can `/report` out of the box; grant `staffcore.report.exempt` to staff so their names cannot be filed against. Reports resolved as REVIEWED or DISMISSED are automatically deleted after `reports.cleanup-resolved-after-hours` (default 12 hours; set to `<= 0` to disable).

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
