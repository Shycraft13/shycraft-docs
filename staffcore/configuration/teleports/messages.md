# `teleports/messages.yml`

Location: `plugins/StaffCore/teleports/messages.yml`

Chat + action-bar templates for `/tp`, `/tphere`, `/tppos` and `/back`. All
messages support legacy `&` colours and `&#RRGGBB` hex.

Placeholders (substituted per line, not every key uses every placeholder):

- `%player%` target name
- `%sender%` staff member issuing the command (`target-notify` messages)
- `%server%` server id the teleport crosses onto (cross-server variants)
- `%world%` target world (`/tppos`, offline `/tp`)
- `%x%`, `%y%`, `%z%` target coordinates (`/tppos`)

## Sections

```yaml
common:
  no-permission:      "&cNo permission."
  player-not-found:   "&cPlayer not found."
  cannot-target-self: "&cYou cannot teleport to yourself."
  cross-server-off:   "&cCross-server teleport is disabled on this network."
  no-safe-location:   "&cNo safe location found near the target."
  blocked-world:      "&cThat world is blocked for teleports."

tp:
  usage:              "&#F97603Usage: &#FCE300/tp <player>"
  success:            "&#00FC00&lTP &r&7» &fTeleported to &#00FC99%player%&f."
  success-offline:    "&#00FC00&lTP &r&7» &fTeleported to &#00FC99%player%&f's last location &7(offline)&f."
  cross-server:       "&#00FC00&lTP &r&7» &fTransferring you to &#00FC99%server%&f to reach &#00FC99%player%&f..."
  target-notify:      "&#00FC00&lTP &r&7» &#00FC99%sender% &fteleported to you."

tphere:
  usage:              "&#F97603Usage: &#FCE300/tphere <player>"
  success:            "&#00FC00&lTP &r&7» &fPulled &#00FC99%player% &fto your location."
  cross-server:       "&#00FC00&lTP &r&7» &fPulling &#00FC99%player% &ffrom &#00FC99%server%&f..."
  target-must-be-online: "&cCannot pull an offline player. Use /tp <player> to reach them instead."
  target-notify:      "&#00FC00&lTP &r&7» &fYou have been teleported to &#00FC99%sender%&f."

tppos:
  usage:              "&#F97603Usage: &#FCE300/tppos <x> <y> <z> [world] [server]"
  success:            "&#00FC00&lTP &r&7» &fTeleported to &#FCE300%x% %y% %z% &fin &#00FC99%world%&f."
  cross-server:       "&#00FC00&lTP &r&7» &fTransferring you to &#00FC99%server%&f..."
  invalid-coords:     "&cInvalid coordinates."
  world-not-found:    "&cWorld &f%world% &cnot found on this server."
  server-not-found:   "&cServer &f%server% &cnot found in the network."

back:
  no-history:         "&cNo previous location on record."
  success:            "&#00FC00&lBACK &r&7» &fReturned to your previous location."
  cross-server:       "&#00FC00&lBACK &r&7» &fReturning to &#00FC99%server%&f..."
```

`common` keys are shared across every teleport command. The four
command-scoped sections (`tp`, `tphere`, `tppos`, `back`) only fire from that
one command.

`/staffcore reload` reloads this file alongside every other config; new
values apply immediately with no restart.
