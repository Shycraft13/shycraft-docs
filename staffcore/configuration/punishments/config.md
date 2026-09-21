# `punishments/config.yml`

Location: `plugins/StaffCore/punishments/config.yml`

Punishment-specific behaviour: broadcast routing, time formatting, per-command
defaults, and mute enforcement toggles.

```yaml
punishments:
  broadcast: true
  broadcast-to-console: true
  respect-bypass-permissions: true

time:
  permanent-label: "permanent"
  suffix-day:      "d"
  suffix-hour:     "h"
  suffix-minute:   "m"
  suffix-second:   "s"
  separator:       " "
  max-units:       2

ban:
  default-reason: "No reason provided."

mute:
  default-reason: "No reason provided."

  blocked-commands:
    - "msg"
    - "reply"
    - "r"
    - "tell"
    - "whisper"
    - "pm"
    - "w"
    - "me"
    - "say"

  block-signs: true
  block-books: true
  block-anvil-rename: true

  intercept-with-packetevents: true
  fallback-chat-event: true

  voicechat:
    enabled: true

warn:
  default-reason: "No reason provided."
  page-size: 10

kick:
  default-reason: "No reason provided."
```

## `punishments:`

| Key | Description |
| --- | --- |
| `broadcast` | Broadcast bans, mutes, warns, kicks to players with `staffcore.notify`. |
| `broadcast-to-console` | Also send broadcasts to the server console. |
| `respect-bypass-permissions` | If true, staff members with `staffcore.<action>.bypass` cannot be targeted by other staff. Overridden by `staffcore.admin`. |

## `time:`

Controls how durations are rendered in messages and screens. `max-units: 2`
means `"1d 3h"`; `max-units: 4` would render `"1d 3h 25m 7s"` for the same
duration.

## `ban:` / `warn:` / `kick:`

| Key | Description |
| --- | --- |
| `default-reason` | Reason shown when a staff member omits the reason argument. |
| `warn.page-size` | Number of entries per page in `/warns` chat output. |

## `mute:`

| Key | Description |
| --- | --- |
| `default-reason` | Reason when `/mute` is used without a reason. |
| `blocked-commands` | Commands the muted player cannot use. Leading `/` is omitted, case-insensitive. |
| `block-signs` | Refuse sign edits from muted players. |
| `block-books` | Refuse book writing from muted players. |
| `block-anvil-rename` | Cancel the rename output of any anvil action a muted player performs. Enchant / repair combines still pass through. |
| `intercept-with-packetevents` | Primary chat block: intercept chat at the earliest point, so chat channel / formatter / logger plugins never see the muted player's message. Requires a server restart to toggle. |
| `fallback-chat-event` | Belt-and-suspenders fallback: also cancel the async chat event at LOWEST priority. |
| `voicechat.enabled` | Block the microphone via Simple Voice Chat. Auto-disables at runtime if the voicechat plugin is missing. |
