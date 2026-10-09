# `reports/gui/list.yml`

Location: `plugins/StaffCore/reports/gui/list.yml`

The paginated report list opened by `/reports` and `/report check <player>`.
Four rows: the first 27 slots hold one book per report, the bottom row is
navigation.

Placeholders: `%total%`, `%page%`, `%maxpage%`, `%filter%`, `%player%`,
`%uuid%`. Inside `REPORT-ITEM` additionally `%id%`, `%reporter%`, `%target%`,
`%message%`, `%preview%`, `%server%`, `%date%`, `%status%` and
`%status-color%`.

```yaml
GUI:
  TITLE: "&8ʀᴇᴘᴏʀᴛѕ"
  TITLE-TARGET: "&8%player%'s ʀᴇᴘᴏʀᴛѕ"

LOADING:
  MATERIAL: CLOCK
  SLOT: 31
  TITLE: "&#AAAAAALoading..."
  LORE:
    - "&7Fetching reports"

EMPTY:
  MATERIAL: BARRIER
  SLOT: 31
  TITLE: "&cNo reports"
  LORE:
    - "&7Nothing to review."

PREV-PAGE:
  MATERIAL: ARROW
  SLOT: 27
  TITLE: "&#FC0000&lPREVIOUS PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fGo to the previous page."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"

FILTER:
  MATERIAL: HOPPER
  SLOT: 30
  TITLE: "&#00A4FC&lFILTER"
  CYCLE:
    - ALL
    - NEW
    - REVIEWED
    - DISMISSED
  LORE-HEADER:
    - "&7Status filter"
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
    - "&fTotal reports: &#FCE300%total%"
    - "&fFilter: &#00A4FC%filter%"
    - "&fUUID: &#AAAAAA%uuid%"

INFO:
  MATERIAL: WRITABLE_BOOK
  SLOT: 31
  TITLE: "&#AAAA00&lREPORTS"
  LORE:
    - "&7Network-wide overview"
    - ""
    - "&#AAAA00Information"
    - "&fTotal: &#FCE300%total%"
    - "&fFilter: &#00A4FC%filter%"
    - "&fPage: &#FCE300%page% &7/ &#FCE300%maxpage%"

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
  TITLE: "&#00FC00&lNEXT PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#00FC00Information"
    - "&fGo to the next page."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Next Page"

REPORT-ITEM:
  MATERIAL: WRITABLE_BOOK
  MATERIAL-REVIEWED: BOOK
  MATERIAL-DISMISSED: PAPER

  STATUS-COLOR-NEW:       "&#FC0000"
  STATUS-COLOR-REVIEWED:  "&#00A4FC"
  STATUS-COLOR-DISMISSED: "&#AAAAAA"

  TITLE: "%status-color%&l%target%"
  LORE:
    - "&7Report &#FCE300#%id%"
    - ""
    - "%status-color%Information"
    - "&fBy:     &#00FC99%reporter%"
    - "&fDate:   &#AAAAAA%date%"
    - "&fServer: &#AAAAAA%server%"
    - "&fStatus: %status-color%%status%"
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Open"
```
