# `economy/announcement/messages.yml`

Location: `plugins/EconomyCore/economy/announcement/messages.yml`

```yaml
messages:
  # ── /announce ────────────────────────────────────────────────────────────
  announce-no-permission: "&cYou don't have permission."
  announce-usage:         "&cUsage: /announce <message>"

  # ── /reminder ────────────────────────────────────────────────────────────
  reminder-no-permission: "&cYou don't have permission."
  reminder-usage:         "&cUsage: /reminder <name>"
  # Placeholders: %reminders% (comma separated list, or "(none)" fallback).
  reminder-list:          "&7Reminders: %reminders%"
  reminder-none-fallback: "&8(none)"
  # Placeholders: %name%, %reminders% (comma separated list).
  reminder-unknown:       "&cUnknown reminder '&f%name%&c'. Available: %reminders%"
  # Placeholders: %name%
  reminder-sent:          "&#00A4FC&lADMIN &r&7» &fSent reminder &#00FC99%name%&f."

  # ── /economy reload ──────────────────────────────────────────────────────
  economy-no-permission:  "&cYou don't have permission."
  economy-usage:          "&cUsage: /economy reload"
  economy-reloaded:       "&#00A4FC&lECONOMY &r&7» &fConfig reloaded."
```
