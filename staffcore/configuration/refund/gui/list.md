# `refund/gui/list.yml`

Location: `plugins/StaffCore/refund/gui/list.yml`

Per-category snapshot list. Opened by clicking a category tile in the
[category picker](category.md). Snapshots fill the top rows; the bottom
row is reserved for navigation.

Placeholders in `TITLE` / `LORE`: `%player%`, `%category%`, `%page%`, `%maxpage%`.
Placeholders on `ITEM` only: `%ordinal%`, `%date%`, `%server%`, `%world%`, `%x%`, `%y%`, `%z%`.

```yaml
GUI:
  ROWS: 4
  ITEMS-PER-PAGE: 27
  TITLE: "&8%category% ʙᴀᴄᴋᴜᴘѕ"

ITEM:
  MATERIAL: BARREL
  TITLE: "&#00A4FC&l#%ordinal% &8- &#00A4FC&l%date%"
  LORE:
    - "&7Backup"
    - ""
    - "&#00A4FCInformation"
    - "&fServer: &#00A4FC%server%"
    - "&fWorld: &#00A4FC%world%"
    - "&fCoords: &#00A4FC%x%&f, &#00A4FC%y%&f, &#00A4FC%z%"
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Open Actions"

EMPTY:
  SLOT: 13
  MATERIAL: BARRIER
  TITLE: "&#FC0000&lNO BACKUPS"
  LORE:
    - "&7Empty"
    - ""
    - "&#FC0000Information"
    - "&fNo &f%category% &fbackups"
    - "&fexist for &#00A4FC%player%&f yet."

TARGET-HEAD:
  SLOT: 31
  TITLE: "&#00A4FC&l%player%"
  LORE:
    - "&7Target"
    - ""
    - "&#00A4FCInformation"
    - "&fCategory: &#00A4FC%category%"

BACK:
  SLOT: 27
  MATERIAL: RED_STAINED_GLASS_PANE
  TITLE: "&#FC0000&lBACK"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fReturn to the category picker."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to go back"

PREV-PAGE:
  MATERIAL: ARROW
  TITLE: "&#FC0000&lPREVIOUS PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fGo to page &#FC0000%page%&f."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to go back"

NEXT-PAGE:
  SLOT: 35
  MATERIAL: ARROW
  TITLE: "&#00FC00&lNEXT PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#00FC00Information"
    - "&fGo to page &#00FC00%page%&f."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to go forward"
```

## Sections

| Section | Purpose |
| --- | --- |
| `GUI.ROWS` | Chest height, 1-6. Default `4`. |
| `GUI.ITEMS-PER-PAGE` | Snapshots per page. Default `rows*9 - 9` (top rows), capped to the chest size. Lower this if you widened the nav row. |
| `GUI.TITLE` | Window title. `%category%` is the label of the current category (`DEATH`, `JOIN`, `QUIT`, `ENDERCHEST`). |
| `ITEM` | Item template rendered once per snapshot. `%ordinal%` is 1-based; `%date%` is the snapshot timestamp; `%server%` / `%world%` / `%x%` / `%y%` / `%z%` describe where the snapshot was captured. |
| `EMPTY` | Placeholder shown when the category has no snapshots yet. |
| `TARGET-HEAD` | Player head in the nav row rendered with the target's real skin. |
| `BACK` | Nav button that returns to the category picker. On page > 0 the same slot renders as `PREV-PAGE` instead. |
| `PREV-PAGE` | Rendered at `BACK`'s slot on any page after the first. `%page%` shows the destination page. |
| `NEXT-PAGE` | Rendered only when a next page exists. |

Small-caps font (paste characters directly, don't type them):
`ᴀʙᴄᴅᴇꜰɢʜɪᴊᴋʟᴍɴᴏᴘǫʀѕᴛᴜᴠᴡxʏᴢ`
