# `punishments/config.yml`

Location: `plugins/StaffCore/punishments/config.yml`

Punishment-specific behaviour: broadcast routing, time formatting, per-command
defaults, and mute enforcement toggles.

```yaml
punishments:
  broadcast: true

  broadcast-to-console: true

  respect-bypass-permissions: true

  webhook:
    url: ""
    username: "StaffCore"
    timeout-ms: 5000
    avatar-url-template: "https://mc-heads.net/avatar/%uuid%/128"
    colors:
      ban:    15158332
      unban:   3066993
      mute:   15105570
      unmute:  3066993
      warn:   15844367
      unwarn:  3066993
      kick:   10038562

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
  all-as-ip-ban: false

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

## `punishments.webhook:` — Discord audit log

One Discord webhook logs every ban, unban, tempban, mute, unmute, tempmute,
warn, unwarn and kick to a single channel. Type is signalled by the embed
color and the emoji in the title.

Fires from the origin server only — a network with multiple backends still
posts each action exactly once (the cross-server replay path does not
re-emit).

| Key | Description |
| --- | --- |
| `url` | Discord webhook URL. Empty string disables the whole feature silently. |
| `username` | Name shown as the webhook sender in Discord. |
| `timeout-ms` | HTTP request timeout for a single POST. |
| `avatar-url-template` | Head avatar URL template. `%uuid%` and `%name%` are substituted. The default uses [mc-heads.net](https://mc-heads.net); the target head becomes the embed thumbnail and the staff head becomes the author icon. |
| `colors.<action>` | Embed color for each action, as a decimal integer. Tempbans reuse `ban`, tempmutes reuse `mute`. A missing key falls back to grey. |

The embed carries the target name, staff name, reason (as a blockquote in
the description), and — for tempbans / tempmutes — the duration and the
expiration date. Warns and unwarns also carry the short warn ID so an
entry in Discord can be matched back to a `/warns` row.

## `time:`

Controls how durations are rendered in messages and screens. `max-units: 2`
means `"1d 3h"`; `max-units: 4` would render `"1d 3h 25m 7s"` for the same
duration.

## `ban:` / `warn:` / `kick:`

| Key | Description |
| --- | --- |
| `default-reason` | Reason shown when a staff member omits the reason argument. |
| `ban.all-as-ip-ban` | `true` = every ban also bans every IP the player was ever seen on, so no account can join from those IPs until the ban ends or `/unban` lifts it. Other accounts already online from one of those IPs are kicked with the same ban screen. `false` (default) = only bans issued with `--ip` do that. Turning it off later does not lift IP bans that already exist. |
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
