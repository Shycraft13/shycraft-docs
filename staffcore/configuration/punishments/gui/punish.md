# `punishments/gui/punish.yml`

Location: `plugins/StaffCore/punishments/gui/punish.yml`

Layout of the `/punish <player>` template-picker GUI. 4 rows / 36 slots.
Slots 0..26 hold template entries (up to 27 per page). Slots 27..35 are the
navigation row.

**Title / lore placeholders:** `%player%`, `%uuid%`, `%page%`, `%maxpage%`.
**Template item extras:** `%name%`, `%name-upper%`, `%category%`, `%reason%`,
`%tiers%`, `%permission%`, `%color%` (auto per category).

```yaml
GUI:
  TITLE: "&8%player%'s ᴘᴜɴɪѕʜ"

PREV-PAGE:
  MATERIAL: ARROW
  SLOT: 27
  TITLE: "&#00A4FC&lPREV PAGE"
  LORE:
    - "&7Page &f%page% &7/ &f%maxpage%"

FILTER:
  MATERIAL: HOPPER
  SLOT: 30
  TITLE: "&#00A4FC&lFILTER"
  CYCLE:
    - ALL
    - BAN
    - MUTE
    - WARN
    - KICK
  LORE-HEADER:
    - "&7Category filter"
    - ""
    - "&#00A4FCCurrent Selection"
  ACTIVE-PREFIX: "&#00A4FC▶ &f"
  INACTIVE-PREFIX: "&7▶ &f"
  LORE-FOOTER:
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Change"

TARGET-HEAD:
  SLOT: 31
  TITLE: "&#00FC99&l%player%"
  LORE:
    - "&7Target Player"
    - ""
    - "&#00FC99Information"
    - "&fUUID: &#AAAAAA%uuid%"

SORT:
  MATERIAL: CAULDRON
  SLOT: 32
  TITLE: "&#FCE300&lSORT"
  CYCLE:
    - "By Name"
    - "By Category"
  LORE-HEADER:
    - "&7Sort order"
    - ""
    - "&#FCE300Current Selection"
  ACTIVE-PREFIX: "&#FCE300▶ &f"
  INACTIVE-PREFIX: "&7▶ &f"
  LORE-FOOTER:
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Change"

NEXT-PAGE:
  MATERIAL: ARROW
  SLOT: 35
  TITLE: "&#00A4FC&lNEXT PAGE"
  LORE:
    - "&7Page &f%page% &7/ &f%maxpage%"

TEMPLATE-ITEM:
  MATERIAL-BAN:  REDSTONE_BLOCK
  MATERIAL-MUTE: SOUL_SAND
  MATERIAL-WARN: YELLOW_CONCRETE
  MATERIAL-KICK: PISTON

  COLOR-BAN:  "&#FC0000"
  COLOR-MUTE: "&#F97603"
  COLOR-WARN: "&#FCE300"
  COLOR-KICK: "&#00A4FC"

  TITLE: "%color%&l%name-upper%"
  LORE:
    - "&7%category% template"
    - ""
    - "%color%Information"
    - "&fReason: &#FCE300%reason%"
    - "&fLadder steps: &#FCE300%tiers%"
    - "&fPermission: &#AAAAAA%permission%"
    - ""
    - "%color%▶ %color%&l&nCLICK&r %color% to apply"
```

## Section reference

| Section | Purpose |
| --- | --- |
| `GUI.TITLE` | Window title. |
| `PREV-PAGE` / `NEXT-PAGE` | Pagination arrows. Change `SLOT` to relocate. |
| `FILTER` | Cycle-item that filters templates by category. `CYCLE` is the ordered list of options. |
| `TARGET-HEAD` | Player-head slot for the target. Material is always `PLAYER_HEAD`. |
| `SORT` | Cycle-item for sort order. |
| `TEMPLATE-ITEM` | Rendered per template in the picker. Per-category material and colour override the default. `%color%` in `TITLE` / `LORE` resolves to the matching `COLOR-<category>`. |
