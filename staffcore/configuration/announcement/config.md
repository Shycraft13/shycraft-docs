# `announcement/config.yml`

Location: `plugins/StaffCore/announcement/config.yml`

`/announce <message>` renders a title, a subtitle, a chat line and a sound.
`/broadcast <message>` is the chat-only version for shorter notices. Both are
network-wide: run one on any server and every online player sees it once.

Placeholders in every template: `%message%` (what the staff member typed) and
`%staff%` (the sender name, `console` when run from console).

```yaml
announcement:
  cross-server: true

ANNOUNCE:
  USAGE: "&cUsage: /announce <message>"
  SOUND: "UI_TOAST_CHALLENGE_COMPLETE"

  TITLE:
    ENABLED:  true
    TEXT:     "&#00A4FC&lANNOUNCE"
    SUBTITLE: "&f%message%"
    FADE-IN:  250
    STAY:     3500
    FADE-OUT: 750

  CHAT:
    ENABLED: true
    FORMAT:  "&#00A4FC&lANNOUNCE &r&7» &f%message%"

BROADCAST:
  USAGE: "&cUsage: /broadcast <message>"
  FORMAT: "&e&lBROADCAST &r&7» &f%message%"
  SOUND: ""
```
