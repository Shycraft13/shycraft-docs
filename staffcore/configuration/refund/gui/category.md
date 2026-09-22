# `refund/gui/category.yml`

Location: `plugins/StaffCore/refund/gui/category.yml`

First screen of `/refund <player>`. A 3-row chest with one tile per
category (Death / Join / Quit / Enderchest) plus a target head. Clicking
a category tile opens the [list GUI](list.md) for that category.

Placeholders in `TITLE` / `LORE`: `%player%`.

```yaml
GUI:
  ROWS: 3
  TITLE: "&8ʀᴇғᴜɴᴅ"

CATEGORIES:
  DEATH:
    SLOT: 10
    MATERIAL: SKELETON_SKULL
    TITLE: "&#FC0000&lDEATH"
    LORE:
      - "&7Backups"
      - ""
      - "&#FC0000Information"
      - "&fSnapshots taken when"
      - "&f%player% &fdied."
      - ""
      - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Browse"

  JOIN:
    SLOT: 12
    MATERIAL: LIME_WOOL
    TITLE: "&#00FC00&lJOIN"
    LORE:
      - "&7Backups"
      - ""
      - "&#00FC00Information"
      - "&fSnapshots taken when"
      - "&f%player% &flogged in."
      - ""
      - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Browse"

  QUIT:
    SLOT: 14
    MATERIAL: RED_WOOL
    TITLE: "&#F97603&lQUIT"
    LORE:
      - "&7Backups"
      - ""
      - "&#F97603Information"
      - "&fSnapshots taken when"
      - "&f%player% &flogged out."
      - ""
      - "&#F97603▶ &#F97603&l&nCLICK&r &#F97603to Browse"

  ENDERCHEST:
    SLOT: 16
    MATERIAL: ENDER_CHEST
    TITLE: "&#A303F9&lENDERCHEST"
    LORE:
      - "&7Backups"
      - ""
      - "&#A303F9Information"
      - "&fSnapshots taken when"
      - "&f%player% &fclosed their"
      - "&fenderchest."
      - ""
      - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to Browse"

TARGET-HEAD:
  SLOT: 22
  TITLE: "&#00A4FC&l%player%"
  LORE:
    - "&7Target"
    - ""
    - "&#00A4FCInformation"
    - "&fBrowsing backups for"
    - "&#00A4FC%player%&f."
```

## Sections

| Section | Purpose |
| --- | --- |
| `GUI.ROWS` | Chest height, 1-6. Default `3`. |
| `GUI.TITLE` | Window title. |
| `CATEGORIES.<name>` | One block per category. Turning a category off in [`refund/config.yml`](../config.md) does NOT hide it here; delete the block entirely to hide it. Valid category names: `DEATH`, `JOIN`, `QUIT`, `ENDERCHEST`. |
| `CATEGORIES.<name>.SLOT` | Chest slot (0-indexed). Ignored if two categories point to the same slot: the first-declared one wins. |
| `CATEGORIES.<name>.MATERIAL` | Bukkit material name. Anything valid works. |
| `CATEGORIES.<name>.TITLE` / `.LORE` | Item display. |
| `TARGET-HEAD` | Player head rendered with the target's real skin. Bring up any player's snapshots and their face appears here. |

Small-caps font (paste characters directly, don't type them):
`ᴀʙᴄᴅᴇꜰɢʜɪᴊᴋʟᴍɴᴏᴘǫʀѕᴛᴜᴠᴡxʏᴢ`
