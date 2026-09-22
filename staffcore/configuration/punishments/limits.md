# `punishments/limits.yml`

Location: `plugins/StaffCore/punishments/limits.yml`

Per-group duration caps and cooldowns for `/ban`, `/mute`, `/warn`, `/kick`
and `/punish`. Every staff member is matched against each group by its
`permission` node; a single staff member can match multiple groups at once.

```yaml
reduce-to-limit: true
default-cooldown: 5s
console-cooldown: 1s
default-redo-cooldown: 30s

groups:

  admin:
    permission: staffcore.limit.admin
    tempban:  7d
    tempmute: 7d
    cooldown_ban:  3m
    require_template: true

  moderator:
    permission: staffcore.limit.mod
    tempban:  7d
    tempmute: 7d
    cooldown_ban:  3m
    require_template: true

  helper:
    permission: staffcore.limit.helper
    tempmute: 3d
    cooldown_mute: 10m
    cooldown_warn: 5m
    require_template: true
```

## Global fallbacks

| Key | Description |
| --- | --- |
| `reduce-to-limit` | `true` (default) clamps the requested duration down to the cap silently and executes the command. `false` refuses the command and shows an error. |
| `default-cooldown` | Applied for any action a matched group does not set an explicit `cooldown_<action>` on. Duration format: `5s`, `10m`, `1h`. |
| `console-cooldown` | Cooldown that applies when the server console issues the punishment. Doesn't stop the console from punishing multiple players at once, only prevents double-punishing the same target within the window. |
| `default-redo-cooldown` | Applied when the same staff member removes a target's punishment and immediately re-issues one (per-group `cooldown_redo` overrides this for matched groups). Blank or `0s` disables the redo cooldown entirely. |

## Group fields

Every group needs a `permission` node — everything else is optional.

| Key | Description |
| --- | --- |
| `permission` | Any staff member with this node matches the group. Multiple matches allowed. |
| `tempban` | Maximum temporary-ban duration. Permanent bans require `staffcore.ban.permanent` and are unaffected. |
| `tempmute` | Maximum temporary-mute duration. Permanent mutes require `staffcore.mute.permanent`. |
| `cooldown_ban` | Cooldown between two `/ban` executions by this staff member. |
| `cooldown_mute` | Cooldown between two `/mute` executions. |
| `cooldown_warn` | Cooldown between two `/warn` executions. |
| `cooldown_kick` | Cooldown between two `/kick` executions. |
| `cooldown_redo` | Cooldown after this staff member removes a punishment on a target before they can re-issue one on the same target. Overrides `default-redo-cooldown` for matched groups. |
| `require_template` | If `true`, this staff member can only use `/ban`, `/mute`, `/warn`, `/kick` when the second argument is a template name. Free-form `/ban <player> 7d spam` is refused. |

Duration format: `1s`, `30s`, `10m`, `3h`, `1d`, `7d`, `2w`. Human forms
like `"7 days"` or `"3 hours"` also parse.

## Resolution rules

When a staff member matches multiple groups, the effective limit is derived
per rule:

- **Duration caps** — **highest** match wins. A staff member with both a
  `helper` and a `moderator` group ends up with the moderator's cap.
- **Cooldowns** — **lowest** match wins. Cooldowns are strictest bound.
- **`require_template`** — strict. Any matched group setting it to `true`
  forces the staff member into template-only mode; no other group can
  "unlock" free-form punishments.

## Template override

Templates carry their own permission (`staffcore.template.<name>`, declared
per-template in `punishments/punishments.yml`). If a staff member has that
permission, the template's duration is applied **as-is**, even if it
exceeds the group's `tempban` / `tempmute` cap. Cooldowns still apply.

The reason: templates are admin-designed ladders. Once a staff member is
trusted with a 30-day template, the intent is that they can execute its
full progression, not have every step clamped by their group cap.

## Cross-server + persistence

Cooldown state is stored in the primary database (MySQL / MongoDB / SQLite).
It persists across restarts and is shared across every node in the network:
a staff member who has just used their `/ban` cooldown on one server will
still be on cooldown after switching to another server or after the server
restarts. Expired cooldowns are cleaned up automatically.

## Bypass permissions

All bypass nodes default to `false` — grant them explicitly.

| Node | Effect |
| --- | --- |
| `staffcore.limit.bypass` | Skip the duration cap (temp bans / temp mutes). |
| `staffcore.limit.unlimited` | Skip the duration cap AND every cooldown AND `require_template`. |
| `staffcore.cooldown.bypass` | Skip every cooldown. |
| `staffcore.cooldown.bypass.ban` | Skip only the ban cooldown. |
| `staffcore.cooldown.bypass.mute` | Skip only the mute cooldown. |
| `staffcore.cooldown.bypass.warn` | Skip only the warn cooldown. |
| `staffcore.cooldown.bypass.kick` | Skip only the kick cooldown. |
| `staffcore.admin` | Bypasses everything (same as `staffcore.limit.unlimited`). |

## Feedback messages

The staff-facing feedback lives in
[`punishments/messages.yml`](messages.md) under the `limits:` block:

| Key | When it fires |
| --- | --- |
| `limits.duration-clamped` | `reduce-to-limit: true` and the requested duration was clamped down to the cap. Chat message. |
| `limits.duration-blocked` | `reduce-to-limit: false` and the requested duration exceeded the cap. Action bar + error sound. |
| `limits.require-template` | Staff member is in template-only mode and tried to run a raw `/ban <player> <time>` command. |
| `limits.cooldown-staff` | Staff member's own cooldown for that action is still active. |
| `limits.cooldown-target` | The target has already been punished with that action within the cooldown window (also applies to console via `console-cooldown`). |
| `limits.cooldown-redo` | The staff member just lifted a punishment on this target and the redo cooldown is still active. |

## Reload

`/staffcore reload` reloads `limits.yml` alongside every other config; no
restart needed.
