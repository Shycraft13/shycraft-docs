# `economy/worth/gui/mainmenu.yml`

Location: `plugins/EconomyCore/economy/worth/gui/mainmenu.yml`

```yaml
gui:
  title: "&8ᴡᴏʀᴛʜ %page%/%maxpage%"

item-lore:
  - "&7Server Worth"
  - ""
  - "&#00FC00Information"
  - "&fThis is the &#00FC00Price &fof this"
  - "&fitem when you &#00FC00sell &fit."
  - ""
  - "&#00FC00▶ &fWorth%stack%: &#00FC00%price%"
  - "&#00FC00▶ &fSellmulti%stack%: &#00FC00%sellmulti_price%"

stack-lore:
  - ""
  - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to %action%"

stack:

  suffix: " (%amount%)"
  action-stack: "Stack"
  action-unstack: "Unstack"

prev-page:
  SLOT: 45
  MATERIAL: ARROW
  TITLE: "&#FC0000&lPREVIOUS PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fGo to the previous page."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"

next-page:
  SLOT: 53
  MATERIAL: ARROW
  TITLE: "&#00FC00&lNEXT PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#00FC00Information"
    - "&fGo to the next page."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Next Page"

refresh:
  SLOT: 49
  MATERIAL: ANVIL
  TITLE: "&#00FC00&lREFRESH"
  LORE:
    - "&7Refresh"
    - ""
    - "&#00FC00Information"
    - "&fClick to refresh"
    - "&fthe price list."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Refresh"

sort:
  SLOT: 48
  MATERIAL: HOPPER
  TITLE: "&#FCE300&lSORTING"
  LORE-HEADER:
    - "&7Item Order"
    - ""
    - "&7Current Selection"
  ACTIVE-PREFIX: "&#FCE300▶ &f"
  INACTIVE-PREFIX: "&7▶ &f"
  LORE-FOOTER:
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Change"

  MODES:
    PRICE_HIGH: "Highest Price"
    PRICE_LOW:  "Lowest Price"
    BY_NAME:    "By Name"

filter:
  SLOT: 50
  MATERIAL: CAULDRON
  TITLE: "&#00A4FC&lFILTER"
  LORE-HEADER:
    - "&7Category"
    - ""
    - "&7Current Selection"
  ACTIVE-PREFIX: "&#00A4FC▶ &f"
  INACTIVE-PREFIX: "&7▶ &f"
  LORE-FOOTER:
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Change"

  CATEGORIES:
    ALL:             "All"
    CROPS:           "Crops"
    ORES:            "Ores"
    MOBS:            "Mobs"
    NATURAL:         "Natural"
    ARMOR_AND_TOOLS: "Armor and Tools"
    FISH:            "Fish"
    BOOK:            "Book"
    POTION:          "Potion"
    BLOCKS:          "Blocks"
```
