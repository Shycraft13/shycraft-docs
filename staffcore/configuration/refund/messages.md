# `refund/messages.yml`

Location: `plugins/StaffCore/refund/messages.yml`

Chat + action-bar strings shown by `/refund`. Legacy `&` colours and
`&#RRGGBB` hex are both accepted.

**Placeholders:** `%player%`, `%server%`, `%category%`, `%amount%`,
`%item%`, `%shulkers%`, `%world%`.

Chat is used for command feedback (usage, target not found). Action bar is
used for GUI feedback (permission denies, action results).

```yaml
common:
  no-permission:              "&cYou lack the permission to run this command."
  no-permission-console:      "&cConsole cannot open the refund GUI."
  player-not-found:           "&cPlayer not found."
  cross-server-off-global:    "&cCross-server networking is disabled on this backend."
  cross-server-off-feature:   "&cCross-server refund is disabled for this feature."

refund:
  usage:                      "&7Usage: &f/refund <player>"
  opened:                     "&7Opened refund GUI for &f%player%&7."
  no-backups:                 "&7No backups yet for &f%player%&7 in &f%category%&7."

view:
  loading:                    "&#AAAAAA&lLOADING"
  no-permission-take:         "&cYou lack permission to take items."
  took-item:                  "&7Took &f%amount%x %item%&7."

action:
  no-permission-replace:      "&cYou lack permission for replace."
  no-permission-giveout:      "&cYou lack permission for give-out."
  no-permission-teleport:     "&cYou lack permission for teleport."
  replace-applied:            "&7Replace applied for &f%player%&7."
  replace-applied-remote:     "&7Replace applied on &f%server%&7."
  replace-applied-offline:    "&7Offline replace queued for &f%player%&7."
  replace-failed:             "&cReplace failed: no route to the target."
  giveout-done:               "&7Packed backup into &f%shulkers% shulker(s)&7."
  teleport-done:              "&7Teleported to backup location."
  teleport-cross-off:         "&cCross-server teleport disabled (teleports feature off)."
  teleport-world-missing:     "&cWorld &f%world%&c is not loaded on this backend."
```

## Message keys

| Key | Fires when |
| --- | --- |
| `common.no-permission` | `/refund` invoked without `staffcore.refund.use`. |
| `common.no-permission-console` | `/refund` invoked from console (must be a player). |
| `common.player-not-found` | Target name did not resolve to any known player (not online, not in the local cache, not returned by Mojang). |
| `refund.usage` | `/refund` invoked without arguments. |
| `view.loading` | Item shown while snapshots load for the list GUI. Also used as the fallback label when the item loads from an empty state. |
| `view.no-permission-take` | Clicking a slot in the View GUI without `staffcore.refund.giveout`. |
| `view.took-item` | Action bar after a successful take in the View GUI. |
| `action.no-permission-replace` | Clicking Replace without `staffcore.refund.replace`. |
| `action.no-permission-giveout` | Clicking Give-Out without `staffcore.refund.giveout`. |
| `action.no-permission-teleport` | Clicking Teleport without `staffcore.refund.teleport`. |
| `action.replace-applied` | Replace succeeded and target is on this server (or offline with `.dat` on this node). |
| `action.replace-applied-remote` | Replace was shipped to the target's server (`%server%` filled). |
| `action.replace-applied-offline` | Replace queued as a broadcast (target is offline and their `.dat` lives on another node). |
| `action.replace-failed` | Replace could not be routed (no live target, no local `.dat`, and Redis is unavailable). |
| `action.giveout-done` | Give-Out finished; `%shulkers%` is the number of shulker boxes the backup was packed into. |
| `action.teleport-done` | Same-server teleport to backup location finished. |
| `action.teleport-cross-off` | Backup location is on another server but `features.teleports` is off, blocking cross-server teleport. |
| `action.teleport-world-missing` | Backup location's world is not loaded on this backend. |
