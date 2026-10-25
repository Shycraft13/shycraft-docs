# `inspect/messages.yml`

Location: `plugins/StaffCore/inspect/messages.yml`

Strings shown by `/invsee` and `/echestsee`. Placeholders: `%player%`,
`%server%`, `%mode%`. Everything except `usage` is shown on the action bar.
Read-only viewers can be regular players, so the lines they see are kept plain;
the `opened*` and `applied*` lines only reach staff with the `.edit`
permission.

```yaml
title:
  inv:     "&8%player%'s Inventory"
  echest:  "&8%player%'s Ender Chest"

mode:
  view: "&7read-only"
  edit: "&#F26D6Dedit"

common:
  no-permission:              "&cYou lack the permission to run this command."
  player-not-found:           "&cPlayer not found."
  cannot-target-self:         "&cYou cannot view yourself."
  target-immune:              "&cYou cannot view this player."
  target-private:             "&c%player% does not allow others to view their inventory."
  cross-server-off-global:    "&cThat player is on another server."
  cross-server-off-feature:   "&cThat player is on another server."

invsee:
  usage:                      "&7Usage: &f/invsee <player>"
  viewing:                    "&7Viewing &f%player%&7's inventory"
  opened:                     "&7Opened &f%player%&7's inventory (%mode%&7)."
  opened-offline:             "&7Opened &f%player%&7's inventory offline (%mode%&7)."
  snapshot-pending:           "&7Loading &f%player%&7's inventory..."
  snapshot-timeout:           "&cCould not load %player%'s inventory right now."
  snapshot-failed:            "&cCould not load %player%'s inventory."
  target-offline:             "&c%player% is not online."
  offline-searching:          "&7Loading &f%player%&7's inventory..."
  offline-unavailable:        "&cNo saved inventory found for %player%."
  offline-target-joined:      "&e%player% joined while you were editing offline, changes discarded."
  live-target-left:           "&e%player% left the server, inspect window closed."
  applied:                    "&aEdits applied to &f%player%&a's inventory."
  applied-remote:             "&aEdits shipped to &f%player% &aon &f%server%&a."
  applied-offline:            "&aOffline edits written for &f%player%&a."
  apply-failed:               "&cCould not ship edits for %player%."

echestsee:
  usage:                      "&7Usage: &f/echestsee <player>"
  viewing:                    "&7Viewing &f%player%&7's ender chest"
  opened:                     "&7Opened &f%player%&7's ender chest (%mode%&7)."
  opened-offline:             "&7Opened &f%player%&7's ender chest offline (%mode%&7)."
  snapshot-pending:           "&7Loading &f%player%&7's ender chest..."
  snapshot-timeout:           "&cCould not load %player%'s ender chest right now."
  snapshot-failed:            "&cCould not load %player%'s ender chest."
  offline-searching:          "&7Loading &f%player%&7's ender chest..."
  offline-unavailable:        "&cNo saved ender chest found for %player%."
  offline-target-joined:      "&e%player% joined while you were editing offline, changes discarded."
  live-target-left:           "&e%player% left the server, inspect window closed."
  applied:                    "&aEdits applied to &f%player%&a's ender chest."
  applied-remote:             "&aEdits shipped to &f%player% &aon &f%server%&a."
  applied-offline:            "&aOffline edits written for &f%player%&a."
  apply-failed:               "&cCould not ship edits for %player%."
```
