# `spy/config.yml`

Location: `plugins/StaffCore/spy/config.yml`

Social spy. `/spy <player>` toggles spying on that player; while it is active
the staff member sees every chat message the target writes, every private
message they send and receive, and every command they run. `/spy list` shows who
you are spying on, `/spy clear` stops all of it. It keeps working when the target
is on a different server.

Placeholder `%target%` is the player being spied on.

```yaml
spy:
  cross-server: true

CHAT-FORMAT: "&8[&#AAAA00SPY&8] &7%target% &8» &f%message%"
PM-FORMAT:   "&8[&#AAAA00SPY&8] &7%sender% &8→ &7%receiver% &8» &f%message%"
CMD-FORMAT:  "&8[&#AAAA00SPY&8] &7%target% &8» &f%command%"

TOGGLE-ON:   "&#AAAA00&lSPY &r&7» &fNow spying on &f%target%&f."
TOGGLE-OFF:  "&#AAAA00&lSPY &r&7» &fStopped spying on &f%target%&f."
NONE:        "&#AAAA00&lSPY &r&7» &fYou are not spying on anyone."
LIST-HEADER: "&#AAAA00&lSPY &r&7» &fSpying on: &f%players%&f."
CLEARED:     "&#AAAA00&lSPY &r&7» &fCleared your spy list (%count% player(s))."
SELF-DENIED: "&cYou cannot spy on yourself."
```
