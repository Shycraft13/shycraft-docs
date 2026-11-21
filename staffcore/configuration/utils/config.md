# `utils/config.yml`

Location: `plugins/StaffCore/utils/config.yml`

The small staff utilities, gated as a group by `features.utils` in
`config/config.yml`: `/fly`, `/godmode`, `/flyspeed`, `/speed`, `/heal`, `/feed`,
`/repair`, `/near` and `/top`. The commands that take a target work across servers, and an
offline target gets the change the next time they log in.

```yaml
utils:
  cross-server: true

FLY-ENABLED:    "&a&lFLY &r&7» &fEnabled fly for &e%target%&f."
FLY-DISABLED:   "&a&lFLY &r&7» &fDisabled fly for &e%target%&f."
FLY-TOGGLED:    "&a&lFLY &r&7» &fToggled fly for &e%target%&f."
GOD-SELF-ON:    "&#FC0000&lGODMODE &r&7» &fYou are now in godmode."
GOD-SELF-OFF:   "&#FC0000&lGODMODE &r&7» &fYou left godmode."
GOD-ENABLED:    "&#FC0000&lGODMODE &r&7» &fEnabled godmode for &#FCE300%target%&f."
GOD-DISABLED:   "&#FC0000&lGODMODE &r&7» &fDisabled godmode for &#FCE300%target%&f."
GOD-TOGGLED:    "&#FC0000&lGODMODE &r&7» &fToggled godmode for &#FCE300%target%&f."
GOD-TARGET-ON:  "&#FC0000&lGODMODE &r&7» &fYou are now in godmode."
GOD-TARGET-OFF: "&#FC0000&lGODMODE &r&7» &fYou left godmode."
GOD-ACTION-BAR: "&#FC0000&lGODMODE"
FLYSPEED-SET:   "&a&lFLYSPEED &r&7» &fSet to &e%speed%&f for &e%target%&f."
FLYSPEED-RESET: "&a&lFLYSPEED &r&7» &fReset for &e%target%&f."
SPEED-SET:      "&a&lSPEED &r&7» &fSet to &e%speed%&f for &e%target%&f."
SPEED-RESET:    "&a&lSPEED &r&7» &fReset for &e%target%&f."
HEALED:         "&a&lHEAL &r&7» &fHealed &e%target%&f."
FED:            "&a&lFEED &r&7» &fFed &e%target%&f."
REPAIRED:       "&a&lREPAIR &r&7» &fRepaired &e%target%&f's held item."
REPAIRED-EMPTY: "&cNo item in hand to repair."
PENDING-QUEUED: "&a&lSTAFF &r&7» &e%target% &fis offline. The action will fire when they next join."
TARGET-NOTIFY:  "&a&lSTAFF &r&7» &fA staff member applied &e%op% &fto you."

INVALID-SPEED:  "&cSpeed must be 0-10 or 'reset'."
TOP-NO-BLOCK:   "&cNo solid block above you."
PLAYERS-ONLY:   "&cOnly players can use this command."

NEAR-HEADER:    "&a&lNEAR &r&7» &f%count% player(s) within %radius% blocks:"
NEAR-LINE:      "  &7- &f%name% &7(&f%distance%&7m)"
NEAR-NONE:      "&a&lNEAR &r&7» &fNo other players within %radius% blocks."
TOP-DONE:       "&a&lTOP &r&7» &fTeleported to the highest block."

NEAR-MAX-RADIUS: 500
```
