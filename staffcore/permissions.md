# Permissions

Every node follows the `staffcore.<feature>` scheme. Defaults are hardcoded in the plugin (`op` or `false`) and cannot be changed from YAML on purpose. To unregister a node entirely, delete its line from `config/permissions.yml`.

## Base access

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.use` | `op` | Base access to the plugin. Currently not enforced anywhere; reserved for future gating. |
| `staffcore.admin` | `op` | Full access. Wildcard used by templates that have no explicit permission set, and required for `/staffcore push`. |
| `staffcore.notify` | `op` | Receive ban / unban / mute / unmute / warn / kick / template broadcasts. |
| `staffcore.reload` | `op` | Use `/staffcore reload`. |

## Bans

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.ban` | `op` | Use `/ban`. |
| `staffcore.ban.temp` | `op` | Issue temporary bans (`/ban <player> <time> <reason>`). |
| `staffcore.ban.permanent` | `op` | Issue permanent bans (`/ban <player> <reason>`). |
| `staffcore.ban.bypass` | `false` | Immune to being banned. Only respected when `punishments.respect-bypass-permissions: true` (default). Overridden by `staffcore.admin`. |
| `staffcore.unban` | `op` | Use `/unban`. |

## Mutes

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.mute` | `op` | Use `/mute`. |
| `staffcore.mute.temp` | `op` | Issue temporary mutes. |
| `staffcore.mute.permanent` | `op` | Issue permanent mutes. |
| `staffcore.mute.bypass` | `false` | Immune to being muted. |
| `staffcore.unmute` | `op` | Use `/unmute`. |

## Warns

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.warn` | `op` | Use `/warn`. |
| `staffcore.warn.bypass` | `false` | Immune to being warned. |
| `staffcore.unwarn` | `op` | Use `/unwarn`. |
| `staffcore.warns` | `op` | Use `/warns`. |

## Kicks

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.kick` | `op` | Use `/kick`. |
| `staffcore.kick.bypass` | `false` | Immune to being kicked. |

## Inspect (invsee / echestsee)

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.invsee.use` | `op` | Open `/invsee <player>` in read-only mode. |
| `staffcore.invsee.edit` | `op` | Open `/invsee <player>` in edit mode (changes write back to the target). |
| `staffcore.echestsee.use` | `op` | Open `/echestsee <player>` in read-only mode. |
| `staffcore.echestsee.edit` | `op` | Open `/echestsee <player>` in edit mode. |
| `staffcore.inspect.bypass` | `false` | Target-side: cannot be inspected or edited by other staff. `staffcore.admin` overrides. |

## Templates

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.punish` | `op` | Use `/punish` (opens the picker GUI, or applies a named template). |
| `staffcore.template.<name>` | `op` | Per-template permission. Every template in `punishments/punishments.yml` declares its own `permission:` field. The shipped defaults are listed below. |

Shipped template permission nodes (edit `punishments/punishments.yml` to add or rename templates, then register the matching node in `config/permissions.yml`):

| Node | Template | Category |
| --- | --- | --- |
| `staffcore.template.cheating` | `cheating` | Ban |
| `staffcore.template.xray` | `xray` | Ban |
| `staffcore.template.exploiting` | `exploiting` | Ban |
| `staffcore.template.spam` | `spam` | Mute |
| `staffcore.template.threats` | `threats` | Mute |
| `staffcore.template.advertising` | `advertising` | Mute |
| `staffcore.template.minorspam` | `minor-spam` | Warn |
| `staffcore.template.behavior` | `behavior` | Kick |

## Alts

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.alts` | `op` | Use `/alts`. |

## Teleports

Registered by the plugin when `features.teleports: true` in
[`config/config.yml`](configuration/config/config.md).

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.tp` | `op` | Use `/tp <player>`. |
| `staffcore.tphere` | `op` | Use `/tphere <player>`. |
| `staffcore.tppos` | `op` | Use `/tppos <x> <y> <z> [world] [server]`. |
| `staffcore.back` | `op` | Use `/back`. |
| `staffcore.randomtp` | `op` | Use `/randomtp` (teleport to a random online player across the network). |
| `staffcore.tp.offline` | `op` | Teleport to an offline player's last logout position. Denied when off even if `staffcore.tp` is granted. |
| `staffcore.teleport.admin` | `op` | Bypass `teleports.blocked-worlds`. |
| `staffcore.tp.bypass` | `false` | Immune to being pulled by `/tphere`. Overridden by `staffcore.admin`. |

## Chat filters

Registered by the plugin when `features.chat: true` in
[`config/config.yml`](configuration/config/config.md).

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.chat.bypass` | `false` | Skip every chat filter (language, anti-repeat, caps, cooldown, rate limit) and every state update. Overridden by `staffcore.admin`. A bypassing player never counts toward their own anti-repeat or rate-limit buffers, so removing the node re-arms the filters from a clean slate. Also immune to `/chat pause` and `/chat clear`. |
| `staffcore.chat.clear` | `op` | Use `/chat clear` (network-wide chat wipe). |
| `staffcore.chat.pause` | `op` | Use `/chat pause [duration]` and `/chat unpause` (network-wide chat pause toggle). |

## Announcements

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.announce` | `op` | Use `/announce <message>`: full-render network-wide (title + chat + sound). |
| `staffcore.broadcast` | `op` | Use `/broadcast <message>`: chat-only network-wide message. |

## Staff chat

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.staffchat` | `op` | Toggle `/staffchat` AND receive staff chat messages. |

## Spy

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.spy` | `op` | Use `/spy <player\|list\|clear>`: watch a target's chat, private messages (both directions) and executed commands, cross-server. |

## Freeze

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.freeze` | `op` | Use `/freeze <player> [reason]`. Cross-server and offline-aware: an offline target is frozen the moment they log in on any node. |

## Vanish

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.vanish` | `op` | Toggle vanish on yourself (`/vanish`). Persists in the database and follows you across servers. |
| `staffcore.vanish.other` | `op` | Toggle vanish on another player (`/vanish <player>`). |
| `staffcore.vanish.see` | `op` | Target-side: staffer keeps seeing vanished players (staff-see-staff). |

## Utils

Registered by the plugin when `features.utils: true` in
[`config/config.yml`](configuration/config/config.md). Every self / other
node pair follows the same shape: the base node covers the arg-less
"self" variant, the `.other` node covers the `[player]` argument (cross-
server aware, and offline-aware via a pending flag applied on next join).

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.utils.fly` | `op` | Toggle fly on yourself (`/fly`). |
| `staffcore.utils.fly.other` | `op` | Toggle fly on another player (`/fly <player>`). |
| `staffcore.utils.flyspeed` | `op` | Set or reset your own fly speed (`/flyspeed <0-10\|reset>`). |
| `staffcore.utils.flyspeed.other` | `op` | Set another player's fly speed (`/flyspeed <player> <0-10\|reset>`). |
| `staffcore.utils.speed` | `op` | Set or reset your own walk speed (`/speed <0-10\|reset>`). |
| `staffcore.utils.speed.other` | `op` | Set another player's walk speed. |
| `staffcore.utils.heal` | `op` | Heal yourself (`/heal`). |
| `staffcore.utils.heal.other` | `op` | Heal another player. |
| `staffcore.utils.feed` | `op` | Refill your own hunger + saturation (`/feed`). |
| `staffcore.utils.feed.other` | `op` | Refill another player's hunger + saturation. |
| `staffcore.utils.repair` | `op` | Repair the item in your main hand (`/repair`). |
| `staffcore.utils.repair.other` | `op` | Repair the item in another player's main hand. |
| `staffcore.utils.near` | `op` | List nearby players in the current world (`/near [radius]`). Radius capped at 500. |
| `staffcore.utils.top` | `op` | Teleport to the highest solid block above your XZ (`/top`). |

## Reports

Registered by the plugin when `features.reports: true` in
[`config/config.yml`](configuration/config/config.md).

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.report` | `true` | File a `/report <player> <reason>` against another player. Default is TRUE so every player can report. |
| `staffcore.report.exempt` | `false` | Target-side: cannot be reported. Grant this to staff so their name is rejected when a player tries to report them. `staffcore.admin` overrides (so admins are always exempt). |
| `staffcore.reports.review` | `op` | Open `/reports` (network-wide list), `/report check <player>` (per-target list), `/report check #<id>` (single-report detail), and click Dismiss / Mark Reviewed on the detail GUI. |
| `staffcore.report.cooldown-bypass` | `false` | Skip the per-reporter cooldown between filings (`reports.cooldown-seconds` in `reports/config.yml`). |

## Refund

Registered by the plugin when `features.refund: true` in
[`config/config.yml`](configuration/config/config.md).

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.refund.use` | `op` | Open `/refund <player>`. Base access to the refund GUI (category picker + list + view). |
| `staffcore.refund.replace` | `op` | Click the Replace button in the action menu (overwrite the target's inventory / enderchest with the snapshot). |
| `staffcore.refund.giveout` | `op` | Click the Give-Out button (receive the snapshot packed into shulker boxes). Also required to take items out of the View GUI. |
| `staffcore.refund.teleport` | `op` | Click the Teleport button (jump to where the snapshot was captured, cross-server aware when `features.teleports` is also on). |

`staffcore.admin` bypasses all four nodes above. A staff member with
`staffcore.refund.use` but none of the action nodes can still browse and
view snapshots; every action button they lack shows a "no permission"
message on click.

## Gamemodes

Registered by the plugin when `features.gamemodes: true` in
[`config/config.yml`](configuration/config/config.md).

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.gamemode.survival` | `op` | Switch to survival (`/gamemode survival`, `/gm 0`, `/gms`). Required for self and target changes to survival. |
| `staffcore.gamemode.creative` | `op` | Switch to creative. |
| `staffcore.gamemode.adventure` | `op` | Switch to adventure. |
| `staffcore.gamemode.spectator` | `op` | Switch to spectator. |
| `staffcore.gamemode.other` | `op` | Change another player's gamemode. Required in addition to the per-mode node whenever `[player]` is supplied. |
| `staffcore.gamemode.offline` | `op` | Change an offline player's gamemode. Required in addition to `staffcore.gamemode.other` whenever the target is offline. |

`staffcore.admin` bypasses all six nodes. A staff member with only the
per-mode nodes but not `staffcore.gamemode.other` can only change their
own gamemode; adding `staffcore.gamemode.other` unlocks online targets;
adding `staffcore.gamemode.offline` on top of that unlocks `.dat` writes
on offline targets.

## Duration caps + cooldowns

Grant one of the group-matching nodes below to a staff member to gate them
by the matching group in [`punishments/limits.yml`](configuration/punishments/limits.md).
The shipped groups (`admin`, `moderator`, `helper`) are examples; add /
remove groups freely and register a matching node in `config/permissions.yml`.

| Node | Default | Description |
| --- | --- | --- |
| `staffcore.limit.admin` | `false` | Matches the shipped `admin` group. |
| `staffcore.limit.mod` | `false` | Matches the shipped `moderator` group. |
| `staffcore.limit.helper` | `false` | Matches the shipped `helper` group. |
| `staffcore.limit.bypass` | `false` | Skip duration caps entirely. |
| `staffcore.limit.unlimited` | `false` | Skip duration caps AND every cooldown AND `require_template`. |
| `staffcore.cooldown.bypass` | `false` | Skip every cooldown. |
| `staffcore.cooldown.bypass.ban` | `false` | Skip only the ban cooldown. |
| `staffcore.cooldown.bypass.mute` | `false` | Skip only the mute cooldown. |
| `staffcore.cooldown.bypass.warn` | `false` | Skip only the warn cooldown. |
| `staffcore.cooldown.bypass.kick` | `false` | Skip only the kick cooldown. |

## Bypass semantics

- `staffcore.<action>.bypass` only takes effect when `punishments.respect-bypass-permissions: true` in `punishments/config.yml` (default: true).
- A staff member with `staffcore.admin` can always target another staff member regardless of bypass permissions — the wildcard overrides bypasses.
- A player with `staffcore.ban.bypass` who is targeted by `/ban` receives the "cannot target that staff member" error (unless the sender has `staffcore.admin`).
- These bypass nodes exist because tab-completion cross-servers online names, so a staff member with `staffcore.notify` can still accidentally tab-complete another staff member's name into a `/ban`.

## Registering / unregistering nodes

`config/permissions.yml` is a plain list of strings. The plugin only registers nodes present in that list. To hide a feature completely from your permission plugin's suggestions, delete its line.

```yaml
permissions:
  - staffcore.use
  - staffcore.admin
  - staffcore.ban
  # - staffcore.ban.permanent   # commented out = no permanent bans anywhere
  - staffcore.ban.temp
```

Note: the plugin still checks the node at runtime even if you commented it out. Removing the line only hides it from `/lp editor` and similar tools; the actual gate is done in code with the hardcoded default (`op` in almost every case).
