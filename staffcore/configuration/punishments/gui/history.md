# `punishments/gui/history.yml`

Location: `plugins/StaffCore/punishments/gui/history.yml`

Layout of the `/history <player>` viewer GUI. 4 rows / 36 slots. Slots
0..26 hold history entries. Slots 27..35 are the navigation row.

**Title / lore placeholders:** `%player%`, `%uuid%`, `%total%`, `%page%`,
`%maxpage%`.
**History item extras:** `%type%`, `%type-upper%`, `%reason%`, `%staff%`,
`%date%`, `%expires%`, `%color%`, `%id%` (warns only).

```yaml
GUI:
  TITLE: "&8%player%'s ʜɪѕᴛᴏʀʏ"

LOADING:
  MATERIAL: CLOCK
  SLOT: 31
  TITLE: "&#AAAAAALoading..."
  LORE:
    - "&7Fetching history"

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
    - "&7Type filter"
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
    - "&fTotal records: &#FCE300%total%"
    - "&fUUID: &#AAAAAA%uuid%"

SORT:
  MATERIAL: CAULDRON
  SLOT: 32
  TITLE: "&#FCE300&lSORT"
  CYCLE:
    - "Newest first"
    - "Oldest first"
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

HISTORY-ITEM:
  MATERIAL-BAN:  REDSTONE_BLOCK
  MATERIAL-MUTE: SOUL_SAND
  MATERIAL-WARN: PAPER
  MATERIAL-KICK: PISTON

  COLOR-BAN:  "&#FC0000"
  COLOR-MUTE: "&#F97603"
  COLOR-WARN: "&#FCE300"
  COLOR-KICK: "&#00A4FC"

  TITLE: "%color%&l%type-upper%"
  LORE:
    - "&7%type% record"
    - ""
    - "%color%Information"
    - "&fReason: &#FCE300%reason%"
    - "&fStaff:  &#00FC99%staff%"
    - "&fDate:   &#AAAAAA%date%"

  LORE-EXPIRES:
    - "&fExpires: &#FCE300%expires%"

  LORE-EXPIRED:
    - "&fStatus:  &#AAAAAAexpired"
    - "&fExpired: &#AAAAAA%expires%"

  LORE-LIFTED:
    - "&fStatus: &#00FC00lifted"
    - "&fBy:     &#00FC99%lifted-by%"
    - "&fOn:     &#AAAAAA%lifted-at%"

  LORE-ID:
    - "&fID: &#AAAAAA%id%"
```

## Per-state lore appended for bans and mutes

Ban and mute entries render one of three status states beneath the base
`LORE`:

| Section | Used when |
| --- | --- |
| `LORE-EXPIRES` | Still active. `%expires%` renders the remaining time or `permanent`. |
| `LORE-EXPIRED` | The punishment ran out on its own. `%expires%` resolves to the past expiry date. |
| `LORE-LIFTED` | Manually removed via `/unban` or `/unmute`. Placeholders `%lifted-by%` and `%lifted-at%` are available. |

`LORE-ID` is appended for warn entries (which carry the 6-hex-char short id
used by `/unwarn`).
