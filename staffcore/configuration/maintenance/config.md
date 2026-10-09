# `maintenance/config.yml`

Location: `plugins/StaffCore/maintenance/config.yml`

`/maintenance <on|off> <target|all|proxy>` sets or clears maintenance, where
`target` is a single server id (for example `smp1`), `proxy`, or `all` for every
server. Switching it on kicks every player without bypass off the affected
servers with the screen below, and new joins are denied with the same screen.
`off all` also clears entries that were set for a single server.

Bypass is either the `staffcore.maintenance.bypass` permission or the bypass
list, managed with `/maintenance add <player>` and `/maintenance remove
<player>`.

```yaml
hide-kick-log: true

ENABLED-ANNOUNCE:  "&#FF9900&lMAINTENANCE &r&7» &fEnabled on &#00FC99%target%&f."
DISABLED-ANNOUNCE: "&#00FC00&lMAINTENANCE &r&7» &fDisabled on &#00FC99%target%&f."
BYPASS-ADDED:      "&#00FC00&lMAINTENANCE &r&7» &fAdded &#00FC99%player% &fto the bypass list."
BYPASS-REMOVED:    "&#FF9900&lMAINTENANCE &r&7» &fRemoved &#00FC99%player% &ffrom the bypass list."
BYPASS-ALREADY:    "&cPlayer %player% is already on the bypass list."
BYPASS-MISSING:    "&cPlayer %player% is not on the bypass list."
ALREADY-ENABLED:   "&cMaintenance is already enabled on %target%."
ALREADY-DISABLED:  "&cMaintenance is not enabled on %target%."
NOT-FOUND:         "&cPlayer not found."
USAGE: |-
  &cUsage:
  &7- &f/maintenance <on|off> <target|all|proxy>
  &7- &f/maintenance add <player>
  &7- &f/maintenance remove <player>
  &7- &f/maintenance list

LIST-HEADER:        "&#FF9900&lMAINTENANCE &r&7» &fCurrent state"
LIST-NODES-ON:      "&7Enabled on: &f%nodes%"
LIST-NODES-EMPTY:   "&7Enabled on: &f(none)"
LIST-BYPASS:        "&7Bypass (&f%count%&7): &f%names%"
LIST-BYPASS-EMPTY:  "&7Bypass: &f(none)"

kick: |-
  &cThe server is currently under maintenance.

  &7We are working on updates and improvements.
  &7Join our Discord for more information:

  &#00A4FCdiscord.gg/yourserver
```
