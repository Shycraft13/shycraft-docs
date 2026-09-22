# `refund/gui/action.yml`

Location: `plugins/StaffCore/refund/gui/action.yml`

Per-snapshot action menu. Opened by clicking a snapshot entry in the
[list GUI](list.md). Four action buttons plus a back button:

- **Replace** overwrites the target's current inventory / enderchest
  with the snapshot contents. Requires `staffcore.refund.replace`.
- **Give Out** packs the snapshot into shulker boxes and hands them to
  you. Requires `staffcore.refund.giveout`.
- **Teleport** jumps you to where the snapshot was captured. Requires
  `staffcore.refund.teleport`. Cross-server aware (needs `features.teleports`
  in [`config/config.yml`](../../config/config.md) for cross-server jumps).
- **View** opens the [view GUI](view.md) for hands-on browsing. Requires
  `staffcore.refund.giveout` to take items out.

Placeholders in `TITLE` / `LORE`: `%player%`, `%category%`.

```yaml
GUI:
  ROWS: 3
  TITLE: "&8ᴀᴄᴛɪᴏɴѕ"

REPLACE:
  SLOT: 10
  MATERIAL: CHEST
  TITLE: "&#FC0000&lREPLACE"
  LORE:
    - "&7Action"
    - ""
    - "&#FC0000Information"
    - "&fOverwrite &#00A4FC%player%&f's"
    - "&fcurrent &#FC0000%category%&f."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Apply"

GIVEOUT:
  SLOT: 12
  MATERIAL: SHULKER_BOX
  TITLE: "&#FCE300&lGIVE OUT"
  LORE:
    - "&7Action"
    - ""
    - "&#FCE300Information"
    - "&fPack the contents into"
    - "&fshulkers and give them"
    - "&fto you."
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Receive"

TELEPORT:
  SLOT: 14
  MATERIAL: COMPASS
  TITLE: "&#00A4FC&lTELEPORT"
  LORE:
    - "&7Action"
    - ""
    - "&#00A4FCInformation"
    - "&fTeleport to where this"
    - "&fbackup was taken."
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Teleport"

VIEW:
  SLOT: 16
  MATERIAL: ITEM_FRAME
  TITLE: "&#A303F9&lVIEW"
  LORE:
    - "&7Action"
    - ""
    - "&#A303F9Information"
    - "&fBrowse the contents."
    - "&fClicks give you a clone;"
    - "&fthe backup stays intact."
    - ""
    - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to View"

BACK:
  SLOT: 18
  MATERIAL: RED_STAINED_GLASS_PANE
  TITLE: "&#FC0000&lBACK"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fReturn to the backup list."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to go back"
```

## Sections

| Section | Purpose |
| --- | --- |
| `GUI.ROWS` | Chest height, 1-6. Default `3`. |
| `GUI.TITLE` | Window title. |
| `REPLACE` | Replace button. Change the slot / material / text to your liking; the action is fixed. |
| `GIVEOUT` | Give-Out button. |
| `TELEPORT` | Teleport button. |
| `VIEW` | View button (opens the [view GUI](view.md)). |
| `BACK` | Returns to the snapshot list. |

Small-caps font (paste characters directly, don't type them):
`ᴀʙᴄᴅᴇꜰɢʜɪᴊᴋʟᴍɴᴏᴘǫʀѕᴛᴜᴠᴡxʏᴢ`
