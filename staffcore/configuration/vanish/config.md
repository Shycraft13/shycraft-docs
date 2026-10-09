# `vanish/config.yml`

Location: `plugins/StaffCore/vanish/config.yml`

`/vanish [player]` toggles vanish on yourself, or on another staff member with
the `.other` permission. The state follows the player across servers.

A vanished staff member is hidden from everyone without
`staffcore.vanish.see`, joins and quits silently, takes no mob damage, loses no
hunger, and opens containers without the other players seeing the lid move.

```yaml
vanish:
  cross-server: true

  silent-join-quit: true

  silent-pickup: true

  silent-container: true

  no-mob-damage: true

  no-hunger: true

TOGGLE-ON:       "&#00FC99&lVANISH &r&7» &fYou are now hidden."
TOGGLE-OFF:      "&#00FC99&lVANISH &r&7» &fYou are visible again."
TARGET-ON:       "&#00FC99&lVANISH &r&7» &fVanished &#FCE300%target%&f."
TARGET-OFF:      "&#00FC99&lVANISH &r&7» &fRevealed &#FCE300%target%&f."
NOT-FOUND:       "&cPlayer %name% not found."
USAGE:           "&cUsage: /vanish [player]"
ACTION-BAR:      "&#00FC99&lVANISHED"
ACTION-BAR-SECONDS: 5
```
