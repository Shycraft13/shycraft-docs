# `reports/gui/detail.yml`

Location: `plugins/StaffCore/reports/gui/detail.yml`

The single-report view, reached by clicking a report in the list or straight
with `/report check #<id>`. Three rows: the report sits on the middle row, with
`BACK` in the bottom-left corner.

Placeholders: `%id%`, `%reporter%`, `%target%`, `%message%`, `%preview%`,
`%message-length%`, `%server%`, `%date%`, `%status%`, `%status-color%`,
`%resolved-by%` and `%resolved-at%`.

```yaml
GUI:
  TITLE: "&8%target%&8's ʀᴇᴘᴏʀᴛ"

TARGET-HEAD:
  SLOT: 12
  TITLE: "%status-color%&l%target%"
  LORE:
    - "&7Reported Player"
    - ""
    - "%status-color%Information"
    - "&fReport:   &#FCE300#%id%"
    - "&fStatus:   %status-color%%status%"
    - "&fServer:   &#AAAAAA%server%"
    - "&fReported: &#AAAAAA%date%"
  LORE-RESOLVED:
    - "&7Reported Player"
    - ""
    - "%status-color%Information"
    - "&fReport:      &#FCE300#%id%"
    - "&fStatus:      %status-color%%status%"
    - "&fServer:      &#AAAAAA%server%"
    - "&fReported:    &#AAAAAA%date%"
    - ""
    - "%status-color%Resolution"
    - "&fResolved by: &#00FC99%resolved-by%"
    - "&fResolved at: &#AAAAAA%resolved-at%"

REPORTER-HEAD:
  SLOT: 14
  TITLE: "&#00FC99&l%reporter%"
  LORE:
    - "&7Reporter"
    - ""
    - "&#00FC99Information"
    - "&fFiled by &#00FC99%reporter%&f."

DETAILS-ITEM:
  MATERIAL: WRITTEN_BOOK
  SLOT: 13
  TITLE: "&#00A4FC&lREPORT"
  LORE:
    - "&7Full report body"
    - ""
    - "&#00A4FCInformation"
    - "&f%preview%"
    - "&fLength: &#AAAAAA%message-length% chars"
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Open"

BACK:
  MATERIAL: RED_STAINED_GLASS_PANE
  SLOT: 18
  TITLE: "&#FC0000&lBACK"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fReturn to the report list."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"

DISMISS:
  MATERIAL: GRAY_DYE
  SLOT: 11
  TITLE: "&#AAAAAA&lDISMISS"
  LORE:
    - "&7Action"
    - ""
    - "&#AAAAAAInformation"
    - "&fMark this report as dismissed."
    - ""
    - "&#AAAAAA▶ &#AAAAAA&l&nCLICK&r &#AAAAAAto Dismiss"

DISMISS-UNDO:
  MATERIAL: LIME_DYE
  SLOT: 11
  TITLE: "&#00FC00&lUNDO DISMISS"
  LORE:
    - "&7Action"
    - ""
    - "&#00FC00Information"
    - "&fSend this report back to &fOpen."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Reopen"

REVIEWED:
  MATERIAL: LIME_DYE
  SLOT: 15
  TITLE: "&#00A4FC&lMARK REVIEWED"
  LORE:
    - "&7Action"
    - ""
    - "&#00A4FCInformation"
    - "&fMark this report as reviewed."
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Mark"

REVIEWED-UNDO:
  MATERIAL: GRAY_DYE
  SLOT: 15
  TITLE: "&#00FC00&lUNDO REVIEW"
  LORE:
    - "&7Action"
    - ""
    - "&#00FC00Information"
    - "&fSend this report back to &fOpen."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Reopen"
```
