# `economy/money/messages.yml`

Location: `plugins/EconomyCore/economy/money/messages.yml`

```yaml
messages:
  # Shown when the player runs /money (no arguments).
  # Placeholders: %balance% (formatted balance string).
  balance-self:     "&#00A4FC&lMONEY &r&7» &fYour balance: &#FCE300%balance%"

  # Shown when the player runs /money <name> for another player (online or offline).
  # Placeholders: %player% (target's name), %balance% (formatted balance string).
  balance-other:    "&#00A4FC&lMONEY &r&7» &f%player%'s balance: &#FCE300%balance%"

  # Shown when /money <name> targets a name that does not exist in the database.
  player-not-found: "&#FC0000Player not found."

  # ── /moneymanager admin command ──────────────────────────────────────────
  moneymanager-no-permission: "&cNo permission."
  moneymanager-usage:         "&cUsage: /moneymanager <add|set|remove> <player> <amount>"
  moneymanager-invalid-amount: "&cInvalid amount."
  moneymanager-unknown-action: "&cUnknown action. Use add, set, or remove."
  # Placeholders: %amount%, %player%, %total% (all formatted money strings for amount/total).
  moneymanager-added:    "&#00A4FC&lADMIN &r&7» &fAdded &#00FC00%amount% &fto &#00FC99%player%&f. New balance: &#00FC00%total%&f."
  moneymanager-set:      "&#00A4FC&lADMIN &r&7» &fSet &#00FC99%player%&f's balance to &#00FC00%amount%&f."
  moneymanager-removed:  "&#00A4FC&lADMIN &r&7» &fRemoved &#00FC00%amount% &ffrom &#00FC99%player%&f. New balance: &#00FC00%total%&f."
  moneymanager-added-offline:   "&#00A4FC&lADMIN &r&7» &fAdded &#00FC00%amount% &fto offline player &#00FC99%player%&f."
  moneymanager-set-offline:     "&#00A4FC&lADMIN &r&7» &fSet offline player &#00FC99%player%&f's balance to &#00FC00%amount%&f."
  moneymanager-removed-offline: "&#00A4FC&lADMIN &r&7» &fRemoved &#00FC00%amount% &ffrom offline player &#00FC99%player%&f. New balance: &#00FC00%total%&f."
```
