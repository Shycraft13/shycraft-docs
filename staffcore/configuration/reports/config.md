# `reports/config.yml`

Location: `plugins/StaffCore/reports/config.yml`

Settings for the player report system.

| Command | Who | What |
| --- | --- | --- |
| `/report <player> <message...>` | everyone | Files a report. Everything after the player name is the report body. |
| `/report check <player>` | staff | Every report filed about that player. |
| `/reports` | staff | Every report on the network. `/report list` is an alias. |

Reports are stored, so the lists read the same on every server, and a new report
notifies every staff member online anywhere on the network.

```yaml
reports:
  cross-server: true

  cooldown-seconds: 60

  message-min-chars: 3
  message-max-chars: 800

  cleanup-resolved-after-hours: 12

  webhook:
    url: ""
    username: "StaffCore Reports"
    timeout-ms: 5000
    embed-color: 15158332
    avatar-url-template: "https://mc-heads.net/avatar/%uuid%/128"

STAFF-NOTIFY: "&#AAAA00&lREPORT &r&7» &f%reporter% &7reported &f%target%&7: &f%preview%"
```
