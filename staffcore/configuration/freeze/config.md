# `freeze/config.yml`

Location: `plugins/StaffCore/freeze/config.yml`

`/freeze <player> [reason]` toggles freeze on the target, including a target
that is online on another server or offline (an offline target is frozen the
moment they log in).

A frozen player cannot move or take damage, and every movement attempt shows the
action-bar block message. Freeze is a short-lived tool, not a punishment: a full
network restart clears it.

```yaml
freeze:
  cross-server: true

FROZEN-ANNOUNCE:   "&#FF3333&lFREEZE &r&7» &fFroze &#00FC99%target%&f. Reason: &#FCE300%reason%&f."
UNFROZEN-ANNOUNCE: "&#00FC00&lUNFREEZE &r&7» &fUnfroze &#00FC99%target%&f."
TARGET-TITLE:       "&#FF3333&lFROZEN"
TARGET-SUBTITLE:    "&f%reason%"
TARGET-CHAT:        "&#FF3333&lFROZEN &r&7» &fA staff member froze you. Reason: &#FCE300%reason%&f."
TARGET-UNFREEZE:    "&#00FC00&lUNFREEZE &r&7» &fYou have been unfrozen. Move freely again."
MOVE-BLOCKED:       "&cYou are frozen. Contact staff."
COMMAND-BLOCKED:    "&cYou cannot run commands while frozen."
ALLOWED-COMMANDS:
  - "r"
  - "reply"
  - "msg"
  - "tell"
  - "w"
  - "helpop"
QUIT:
  AUTO-PUNISH:      false
  TEMPLATE:         "cheating"
  REASON:           "quit while frozen"

NOT-FOUND:          "&cPlayer %name% not found."
USAGE:              "&cUsage: /freeze <player> [reason]"
DEFAULT-REASON:     "Suspicious activity"
```
