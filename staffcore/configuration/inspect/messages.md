# `inspect/messages.yml`

Location: `plugins/StaffCore/inspect/messages.yml`

Strings shown by `/invsee` and `/echestsee`. Placeholders: `%player%`,
`%server%`, `%mode%`. Every line goes to chat and the action bar, see
[Chat and action bar messages](../config/config.md#chat-and-action-bar-messages).
Read-only viewers can be regular players, so the lines they see are kept plain;
the `opened*` and `applied*` lines only reach staff with the `.edit`
permission.

```yaml
title:
  inv:     "&8%player%'s ɪɴᴠᴇɴᴛᴏʀʏ"
  echest:  "&8%player%'s ᴇɴᴅᴇʀ ᴄʜᴇѕᴛ"

mode:
  view: "&7read-only"
  edit: "&#F26D6Dedit"

common:
  no-permission:              "&cNo permission."
  player-not-found:           "&cPlayer not found."
  cannot-target-self:         "&cYou cannot view yourself."
  target-immune:              "&cYou cannot view this player."
  target-private:             "&c%player% does not allow others to view their inventory."
  cross-server-off-global:    "&cThat player is on another server."
  cross-server-off-feature:   "&cThat player is on another server."

invsee:
  viewing:                    "&#00A4FC&lINVSEE &r&7» &fViewing &#00FC99%player%&f's inventory."
  opened:                     "&#00A4FC&lINVSEE &r&7» &fOpened &#00FC99%player%&f's inventory &7(%mode%&7)&f."
  opened-offline:             "&#00A4FC&lINVSEE &r&7» &fOpened &#00FC99%player%&f's inventory offline &7(%mode%&7)&f."
  snapshot-timeout:           "&cCould not load %player%'s inventory right now."
  snapshot-failed:            "&cCould not load %player%'s inventory."
  target-offline:             "&c%player% is not online."
  offline-unavailable:        "&cNo saved inventory found for %player%."
  offline-target-joined:      "&c%player% joined, edit window closed. Changes go to the live inventory."
  live-target-left:           "&c%player% left the server, inspect window closed."
  applied:                    "&#00FC00&lINVSEE &r&7» &fEdits applied to &#00FC99%player%&f's inventory."
  applied-remote:             "&#00FC00&lINVSEE &r&7» &fEdits shipped to &#00FC99%player% &fon &#00FC99%server%&f."
  applied-offline:            "&#00FC00&lINVSEE &r&7» &fOffline edits written for &#00FC99%player%&f."
  apply-failed:               "&cCould not ship edits for %player%."

echestsee:
  viewing:                    "&#00A4FC&lECHEST &r&7» &fViewing &#00FC99%player%&f's ender chest."
  opened:                     "&#00A4FC&lECHEST &r&7» &fOpened &#00FC99%player%&f's ender chest &7(%mode%&7)&f."
  opened-offline:             "&#00A4FC&lECHEST &r&7» &fOpened &#00FC99%player%&f's ender chest offline &7(%mode%&7)&f."
  snapshot-timeout:           "&cCould not load %player%'s ender chest right now."
  snapshot-failed:            "&cCould not load %player%'s ender chest."
  offline-unavailable:        "&cNo saved ender chest found for %player%."
  offline-target-joined:      "&c%player% joined, edit window closed. Changes go to the live ender chest."
  live-target-left:           "&c%player% left the server, inspect window closed."
  applied:                    "&#00FC00&lECHEST &r&7» &fEdits applied to &#00FC99%player%&f's ender chest."
  applied-remote:             "&#00FC00&lECHEST &r&7» &fEdits shipped to &#00FC99%player% &fon &#00FC99%server%&f."
  applied-offline:            "&#00FC00&lECHEST &r&7» &fOffline edits written for &#00FC99%player%&f."
  apply-failed:               "&cCould not ship edits for %player%."
```
