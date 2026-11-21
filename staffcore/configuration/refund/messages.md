# `refund/messages.yml`

Location: `plugins/StaffCore/refund/messages.yml`

Chat + action-bar strings shown by `/refund`. Legacy `&` colours and
`&#RRGGBB` hex are both accepted.

**Placeholders:** `%player%`, `%server%`, `%category%`, `%amount%`,
`%item%`, `%shulkers%`, `%world%`.

One-line messages go to chat (with their prefix) and to the action bar (without
it), errors in red, see
[Chat and action bar messages](../config/config.md#chat-and-action-bar-messages).

```yaml
common:
  no-permission:              "&cNo permission."
  no-permission-console:      "&cConsole cannot open the refund GUI."
  player-not-found:           "&cPlayer not found."
  cross-server-off-global:    "&cCross-server is disabled on this server."
  cross-server-off-feature:   "&cCross-server refund is disabled."

refund:
  opened:                     "&#00A4FC&lREFUND &r&7» &fOpened the refund GUI for &#00FC99%player%&f."
  no-backups:                 "&#00A4FC&lREFUND &r&7» &fNo backups yet for &#00FC99%player% &fin &#FCE300%category%&f."
  self:                       "&cYou cannot open your own backups."

view:
  loading:                    "&#AAAAAA&lLOADING"
  no-permission-take:         "&cNo permission to take items."
  took-item:                  "&#00A4FC&lREFUND &r&7» &fTook &#FCE300%amount%x %item%&f."
  take-only:                  "&cThis view is take-only."
  cursor-first:               "&cPut down the item on your cursor first."
  drop-blocked:               "&cYou cannot drop items here."

action:
  no-permission-replace:      "&cNo permission to replace."
  no-permission-giveout:      "&cNo permission to give out."
  no-permission-teleport:     "&cNo permission to teleport."
  replace-applied:            "&#00FC00&lREFUND &r&7» &fReplace applied for &#00FC99%player%&f."
  replace-applied-remote:     "&#00FC00&lREFUND &r&7» &fReplace sent to &#00FC99%server%&f."
  replace-applied-offline:    "&#00FC00&lREFUND &r&7» &fOffline replace queued for &#00FC99%player%&f."
  replace-failed:             "&cReplace failed: no route to the target."
  giveout-done:               "&#00FC00&lREFUND &r&7» &fPacked the backup into &#FCE300%shulkers% &fshulker(s)."
  teleport-done:              "&#00FC00&lREFUND &r&7» &fTeleported to the backup location."
  teleport-cross-off:         "&cCross-server teleport is disabled."
  teleport-world-missing:     "&cWorld %world% is not loaded on this server."
```

## Message keys

| Key | Fires when |
| --- | --- |
| `common.no-permission` | `/refund` invoked without `staffcore.refund.use`. |
| `common.no-permission-console` | `/refund` invoked from console (must be a player). |
| `common.player-not-found` | Target name did not resolve to any known player (not online, not in the local cache, not returned by Mojang). |
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
