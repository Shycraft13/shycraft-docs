# `economy/profile/messages.yml`

Location: `plugins/EconomyCore/economy/profile/messages.yml`

```yaml
messages:
  # ── /profilemanager admin command ────────────────────────────────────────
  profilemanager-only-players: "&cOnly players can use this command."
  profilemanager-no-permission: "&cNo permission."
  profilemanager-usage:         "&cUsage: /profilemanager <view|edit|wipe> <player> [...]"
  profilemanager-usage-view:    "&cUsage: /profilemanager view <player>"
  profilemanager-usage-edit:    "&cUsage: /profilemanager edit <player> <kills|deaths|playtime> <add|set|remove> <amount>"
  profilemanager-usage-wipe:    "&cUsage: /profilemanager wipe <player>"
  profilemanager-invalid-amount: "&cInvalid amount."
  profilemanager-unknown-action: "&cUnknown action."
  profilemanager-unknown-field:  "&cUnknown field. Use kills, deaths, or playtime."
  profilemanager-player-not-found: "&cPlayer not found."

  # ── /profilemanager edit — online player ─────────────────────────────────
  # Placeholders on every line: %amount% (raw number for kills/deaths, or formatted
  # time for playtime), %player%, %total% (same formatting as %amount%).
  profilemanager-edit-kills-add:      "&#00A4FC&lADMIN &r&7» &fAdded &#FCE300%amount% &fkills to &#00FC99%player%&f. New total: &#FCE300%total%&f."
  profilemanager-edit-kills-remove:   "&#00A4FC&lADMIN &r&7» &fRemoved &#FCE300%amount% &fkills from &#00FC99%player%&f. New total: &#FCE300%total%&f."
  profilemanager-edit-kills-set:      "&#00A4FC&lADMIN &r&7» &fSet &#00FC99%player%&f's kills to &#FCE300%total%&f."
  profilemanager-edit-deaths-add:     "&#00A4FC&lADMIN &r&7» &fAdded &#FCE300%amount% &fdeaths to &#00FC99%player%&f. New total: &#FCE300%total%&f."
  profilemanager-edit-deaths-remove:  "&#00A4FC&lADMIN &r&7» &fRemoved &#FCE300%amount% &fdeaths from &#00FC99%player%&f. New total: &#FCE300%total%&f."
  profilemanager-edit-deaths-set:     "&#00A4FC&lADMIN &r&7» &fSet &#00FC99%player%&f's deaths to &#FCE300%total%&f."
  profilemanager-edit-playtime-add:   "&#00A4FC&lADMIN &r&7» &fAdded &#FCE300%amount% &fto &#00FC99%player%&f's playtime. New total: &#FCE300%total%&f."
  profilemanager-edit-playtime-remove: "&#00A4FC&lADMIN &r&7» &fRemoved &#FCE300%amount% &ffrom &#00FC99%player%&f's playtime. New total: &#FCE300%total%&f."
  profilemanager-edit-playtime-set:   "&#00A4FC&lADMIN &r&7» &fSet &#00FC99%player%&f's playtime to &#FCE300%total%&f."

  # ── /profilemanager edit — offline player ────────────────────────────────
  profilemanager-edit-kills-add-offline:      "&#00A4FC&lADMIN &r&7» &fAdded &#FCE300%amount% &fkills to offline &#00FC99%player%&f. New total: &#FCE300%total%&f."
  profilemanager-edit-kills-remove-offline:   "&#00A4FC&lADMIN &r&7» &fRemoved &#FCE300%amount% &fkills from offline &#00FC99%player%&f. New total: &#FCE300%total%&f."
  profilemanager-edit-kills-set-offline:      "&#00A4FC&lADMIN &r&7» &fSet offline &#00FC99%player%&f's kills to &#FCE300%total%&f."
  profilemanager-edit-deaths-add-offline:     "&#00A4FC&lADMIN &r&7» &fAdded &#FCE300%amount% &fdeaths to offline &#00FC99%player%&f. New total: &#FCE300%total%&f."
  profilemanager-edit-deaths-remove-offline:  "&#00A4FC&lADMIN &r&7» &fRemoved &#FCE300%amount% &fdeaths from offline &#00FC99%player%&f. New total: &#FCE300%total%&f."
  profilemanager-edit-deaths-set-offline:     "&#00A4FC&lADMIN &r&7» &fSet offline &#00FC99%player%&f's deaths to &#FCE300%total%&f."
  profilemanager-edit-playtime-add-offline:   "&#00A4FC&lADMIN &r&7» &fAdded &#FCE300%amount% &fto offline &#00FC99%player%&f's playtime. New total: &#FCE300%total%&f."
  profilemanager-edit-playtime-remove-offline: "&#00A4FC&lADMIN &r&7» &fRemoved &#FCE300%amount% &ffrom offline &#00FC99%player%&f's playtime. New total: &#FCE300%total%&f."
  profilemanager-edit-playtime-set-offline:   "&#00A4FC&lADMIN &r&7» &fSet offline &#00FC99%player%&f's playtime to &#FCE300%total%&f."
```
