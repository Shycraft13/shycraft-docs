# Sell (`economy/sell/`)

/sell menu, sell history, item prices.

## `economy/sell/config.yml`

```yaml
gui:
  title: "&8ꜱᴇʟʟ ɪᴛᴇᴍꜱ"
  rows: 4
```

## `economy/sell/history/gui/mainmenu.yml`

```yaml
SELL-HISTORY-MENU:
  TITLE: "&8ѕᴇʟʟ ʜɪѕᴛᴏʀʏ %page%/%total%"

prev-page:
  MATERIAL: ARROW
  TITLE: "&#FC0000&lPREVIOUS PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fGo to the previous page"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"

refresh:
  MATERIAL: ANVIL
  TITLE: "&#00FC00&lREFRESH"
  LORE:
    - "&7Refresh"
    - ""
    - "&#00FC00Information"
    - "&fClick to refresh"
    - "&fthe sell history"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Refresh"

sort:
  MATERIAL: HOPPER
  TITLE: "&#FCE300&lSORTING"
  LORE-HEADER:
    - "&7Item Order"
    - ""
    - "&7Current Selection"
  LORE-FOOTER:
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Change"
  ACTIVE-PREFIX: "&#FCE300▶ &f"
  INACTIVE-PREFIX: "&7▶ &f"

  MODES:
    EARNED_HIGH: "Most Earned"
    AMOUNT_HIGH: "Most Sold"
    BY_NAME:     "By Name"

filter:
  MATERIAL: CAULDRON
  TITLE: "&#00A4FC&lFILTER"
  LORE-HEADER:
    - "&7Category"
    - ""
    - "&7Current Selection"
  LORE-FOOTER:
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Change"
  ACTIVE-PREFIX: "&#00A4FC▶ &f"
  INACTIVE-PREFIX: "&7▶ &f"

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

next-page:
  MATERIAL: ARROW
  TITLE: "&#00FC00&lNEXT PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#00FC00Information"
    - "&fGo to the next page"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Next Page"
```

## `economy/sell/history/messages.yml`

```yaml
messages:
  no-history:    "&cYou have no sell history yet."
  other-no-history: "&c%player% has no sell history yet."
  looking-up:    "&7Looking up %player%..."
```

## `economy/sell/messages.yml`

```yaml
messages:
  sold: "&#00FC00+%amount%"
```

## `economy/sell/sounds.yml`

```yaml
sounds:
  sell: "minecraft:entity.player.levelup|1.0|2.0"
  open: "minecraft:block.chest.open|1.0|1.0"
```

