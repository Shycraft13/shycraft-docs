# `economy/bounty/gui/mainmenu.yml`

Location: `plugins/EconomyCore/economy/bounty/gui/mainmenu.yml`

```yaml
gui:
  title: "&8ʙᴏᴜɴᴛɪᴇѕ"

prev-page:
  SLOT: 45
  MATERIAL: ARROW
  TITLE: "&#FC0000&lPREVIOUS PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fGo to the"
    - "&fprevious page"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to go back"

search:
  SLOT: 48
  MATERIAL: OAK_SIGN
  TITLE: "&#00A4FC&lSEARCH"
  LORE:
    - "&7Player Search"
    - ""
    - "&#00A4FCInformation"
    - "&fSearch for a player"
    - "&fby name."
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Search"

search-active:
  SLOT: 48
  MATERIAL: OAK_SIGN
  TITLE: "&#00FC99&lSEARCH"
  LORE:
    - "&7Player Search"
    - ""
    - "&#00FC99Information"
    - "&fFiltering: &#00FC99%query%&f."
    - "&fType empty to clear."
    - ""
    - "&#00FC99▶ &#00FC99&l&nCLICK&r &#00FC99to Search Again"

refresh:
  SLOT: 49
  MATERIAL: SKELETON_SKULL
  TITLE: "&#FC0000&lREFRESH"
  LORE:
    - "&7Bounty List"
    - ""
    - "&#FC0000Information"
    - "&fRefresh the"
    - "&fbounty list."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Refresh"

sort:
  SLOT: 50
  MATERIAL: HOPPER
  TITLE: "&#FCE300&lSORT"
  LORE-HEADER:
    - "&7Listing Order"
    - ""
    - "&7Current Selection"
  LORE-FOOTER:
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Change"
  ACTIVE-PREFIX: "&#FCE300▶ &f"
  INACTIVE-PREFIX: "&7▶ &f"

  MODES:
    HIGHEST:        "Highest"
    LOWEST:         "Lowest"
    ALPHABETICALLY: "Alphabetically"

entry:
  TITLE: "&#FC0000#%position% %name%"
  LORE:
    - "&7Bounty: &#00FC00%amount%"

next-page:
  SLOT: 53
  MATERIAL: ARROW
  TITLE: "&#00FC00&lNEXT PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#00FC00Information"
    - "&fGo to the"
    - "&fnext page"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to go forward"
```
