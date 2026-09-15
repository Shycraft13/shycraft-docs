# `economy/shards/messages.yml`

Location: `plugins/EconomyCore/economy/shards/messages.yml`

```yaml
messages:
  # ── /afk command + AFK zones ─────────────────────────────────────────────
  no-afk-set: "&cAFK location has not been set yet."
  afk-set: "&#00A4FC&lAFK &r&7» &fAFK location has been set."
  teleporting: "&#00A4FC&lAFK &r&7» &fTeleporting to AFK..."
  already-teleporting: "&cYou are already teleporting."
  zone-created: "&#00A4FC&lAFK &r&7» &fAFK zone &#FCE300%name% &fcreated."
  zone-deleted: "&#00A4FC&lAFK &r&7» &fAFK zone &#FCE300%name% &fdeleted."
  zone-not-found: "&cAFK zone not found."
  wand-given: "&#00A4FC&lAFK &r&7» &fLeft-click to set corner 1, right-click to set corner 2."
  pos1-set: "&#00A4FC&lAFK &r&7» &fCorner 1 set at &#FCE300%x%, %y%, %z%&f."
  pos2-set: "&#00A4FC&lAFK &r&7» &fCorner 2 set at &#FCE300%x%, %y%, %z%&f."
  both-corners-needed: "&cSet both corners first."

  # Action bar shown to players in an AFK zone. %time% = formatted countdown.
  actionbar: "&7Next shard in &#A303F9%time%&7."
  shard-reward: "&#A303F9&lAFK &r&7» &f+&#A303F9%amount% &fshards."

  # ── /shards command ──────────────────────────────────────────────────────
  # Placeholders: %shards% = formatted shard count.
  shards-self:  "&#00A4FC&lSHARDS &r&7» &fYour shards: &#FCE300%shards%"
  # Placeholders: %player% = target name, %shards% = formatted shard count.
  shards-other: "&#00A4FC&lSHARDS &r&7» &f%player%'s shards: &#FCE300%shards%"
  shards-player-not-found: "&#FC0000Player not found."

  # ── /shardmanager (admin) ────────────────────────────────────────────────
  admin-no-permission:      "&cNo permission."
  shardmanager-usage:       "&cUsage: /shardmanager <add|set|remove> <player> <amount>"
  shardmanager-invalid-amount: "&cInvalid amount."
  shardmanager-player-not-found: "&cPlayer not found."
  shardmanager-unknown-action:   "&cUnknown action. Use add, set, or remove."
  # Placeholders: %amount% (formatted), %player%, %total% (formatted new total).
  shardmanager-added:       "&#00A4FC&lADMIN &r&7» &fAdded &#A303F9%amount% &fshards to &#00FC99%player%&f. New total: &#A303F9%total%&f."
  shardmanager-set:         "&#00A4FC&lADMIN &r&7» &fSet &#00FC99%player%&f's shards to &#A303F9%amount%&f."
  shardmanager-removed:     "&#00A4FC&lADMIN &r&7» &fRemoved &#A303F9%amount% &fshards from &#00FC99%player%&f. New total: &#A303F9%total%&f."
  shardmanager-added-offline:   "&#00A4FC&lADMIN &r&7» &fAdded &#A303F9%amount% &fshards to offline player &#00FC99%player%&f."
  shardmanager-set-offline:     "&#00A4FC&lADMIN &r&7» &fSet offline player &#00FC99%player%&f's shards to &#A303F9%amount%&f."
  shardmanager-removed-offline: "&#00A4FC&lADMIN &r&7» &fRemoved &#A303F9%amount% &fshards from offline player &#00FC99%player%&f. New total: &#A303F9%total%&f."

  # ── /afkmanager (admin) ──────────────────────────────────────────────────
  afkmanager-no-permission:   "&cYou don't have permission."
  afkmanager-usage:           "&cUsage: /afkmanager <setafk|afkarea>"
  afkmanager-usage-afkarea:   "&cUsage: /afkmanager afkarea <wand|create <name>|delete <name>>"
  afkmanager-usage-create:    "&cUsage: /afkmanager afkarea create <name>"
  afkmanager-usage-delete:    "&cUsage: /afkmanager afkarea delete <name>"
  afkmanager-world-mismatch:  "&cBoth corners must be in the same world."
```
