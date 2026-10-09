# `refund/gui/confirm.yml`

Location: `plugins/StaffCore/refund/gui/confirm.yml`

Confirmation step in front of **Replace** and **Give Out** in the
[action menu](action.md). Both actions share this one menu; the summary
text changes with the action.

- **Cancel** returns to the action menu.
- **Confirm** runs the action. Your permission for it is checked again on
  this click.

Set `ENABLED: false` to skip the step, the buttons in the action menu then
run straight away. If the `CONFIRM` button is missing or sits outside the
window, the step is skipped as well and a warning goes to the console.

Placeholders in `TITLE` / `LORE`: `%player%`, `%category%`, `%category-title%`, `%action%`
(`REPLACE` or `GIVE OUT`), `%date%` (when the backup was taken).
`%category%` is the category as plain text (`Death`), `%category-title%` the same in small caps for window titles (`ᴅᴇᴀᴛʜ`).

```yaml
ENABLED: true

GUI:
  ROWS: 3
  TITLE: "&8ᴄᴏɴꜰɪʀᴍ"

CANCEL:
  SLOT: 11
  MATERIAL: RED_STAINED_GLASS_PANE
  TITLE: "&#FC0000&lCANCEL"
  LORE:
    - "&7Action"
    - ""
    - "&#FC0000Information"
    - "&fCancel and return to"
    - "&fthe action menu."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Cancel"

SUMMARY:
  SLOT: 13
  MATERIAL: PAPER
  TITLE: "&#FCE300&lSUMMARY"
  LORE-REPLACE:
    - "&7Preview"
    - ""
    - "&#FCE300Information"
    - "&fAction:   &#FC0000%action%"
    - "&fPlayer:   &#00A4FC%player%"
    - "&fCategory: &#00FC99%category%"
    - "&fBackup:   &7%date%"
    - ""
    - "&fOverwrites the player's"
    - "&fcurrent %category%."
  LORE-GIVEOUT:
    - "&7Preview"
    - ""
    - "&#FCE300Information"
    - "&fAction:   &#FCE300%action%"
    - "&fPlayer:   &#00A4FC%player%"
    - "&fCategory: &#00FC99%category%"
    - "&fBackup:   &7%date%"
    - ""
    - "&fPacks the backup into"
    - "&fshulkers and gives them"
    - "&fto you."

CONFIRM:
  SLOT: 15
  MATERIAL: LIME_STAINED_GLASS_PANE
  TITLE: "&#00FC00&lCONFIRM"
  LORE:
    - "&7Action"
    - ""
    - "&#00FC00Information"
    - "&fRun &#00FC00%action% &ffor"
    - "&f&#00A4FC%player%&f's %category%."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Confirm"
```

## Sections

| Section | Purpose |
| --- | --- |
| `ENABLED` | `true` asks before Replace and Give Out. `false` skips this menu. Default `true`. |
| `GUI.ROWS` | Chest height, 1-6. Default `3`. |
| `GUI.TITLE` | Window title. |
| `CANCEL` | Back to the action menu. |
| `SUMMARY` | Info item. `LORE-REPLACE` is shown for Replace, `LORE-GIVEOUT` for Give Out. |
| `CONFIRM` | Runs the action. Without it the menu is skipped. |

Small-caps font (paste characters directly, don't type them):
`ᴀʙᴄᴅᴇꜰɢʜɪᴊᴋʟᴍɴᴏᴘǫʀѕᴛᴜᴠᴡxʏᴢ`
