# Sell Multiplier (`economy/sellmulti/`)

Rank-based earning bonuses on top of the base worth.

## `economy/sellmulti/config.yml`

```yaml
sellmulti:
  multiplier-per-level: 0.1
  thresholds:
    - 25000
    - 150000
    - 500000
    - 1000000
    - 5000000
    - 25000000
    - 250000000
    - 550000000
    - 850000000
    - 1000000000
    - 2000000000
    - 4000000000
    - 8000000000
    - 10000000000
    - 20000000000
    - 40000000000
    - 80000000000
    - 160000000000
    - 320000000000
    - 640000000000
```

## `economy/sellmulti/gui/overview.yml`

```yaml
OVERVIEW-MENU:
  SIZE: 27
  TITLE: "&8ѕᴇʟʟ ᴍᴜʟᴛɪᴘʟɪᴇʀ"
  BUTTONS:
    CROPS:
      SLOT: 9
      MATERIAL: WHEAT
      TITLE: "&#00FC00&lCROPS"
      LORE:
        - "&7Sell Multiplier"
        - ""
        - "&#00FC00Information"
        - "&fLevel: &#FCE300%level% &f/ &#FCE300%max_level%"
        - "&fMultiplier: &#00FC00%multiplier%"
        - ""
        - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to View Progress"
    ORES:
      SLOT: 10
      MATERIAL: DIAMOND_ORE
      TITLE: "&#00A4FC&lORES"
      LORE:
        - "&7Sell Multiplier"
        - ""
        - "&#00A4FCInformation"
        - "&fLevel: &#FCE300%level% &f/ &#FCE300%max_level%"
        - "&fMultiplier: &#00A4FC%multiplier%"
        - ""
        - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto View Progress"
    MOBS:
      SLOT: 11
      MATERIAL: BONE
      TITLE: "&#FC0000&lMOBS"
      LORE:
        - "&7Sell Multiplier"
        - ""
        - "&#FC0000Information"
        - "&fLevel: &#FCE300%level% &f/ &#FCE300%max_level%"
        - "&fMultiplier: &#FC0000%multiplier%"
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to View Progress"
    NATURAL:
      SLOT: 12
      MATERIAL: OAK_LEAVES
      TITLE: "&#00FC00&lNATURAL"
      LORE:
        - "&7Sell Multiplier"
        - ""
        - "&#00FC00Information"
        - "&fLevel: &#FCE300%level% &f/ &#FCE300%max_level%"
        - "&fMultiplier: &#00FC00%multiplier%"
        - ""
        - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to View Progress"
    ARMOR_AND_TOOLS:
      SLOT: 13
      MATERIAL: GOLDEN_HELMET
      TITLE: "&7&lARMOR & TOOLS"
      LORE:
        - "&7Sell Multiplier"
        - ""
        - "&7Information"
        - "&fLevel: &#FCE300%level% &f/ &#FCE300%max_level%"
        - "&fMultiplier: &7%multiplier%"
        - ""
        - "&7▶ &7&l&nCLICK&r &7to View Progress"
    FISH:
      SLOT: 14
      MATERIAL: COD
      TITLE: "&#00A4FC&lFISH"
      LORE:
        - "&7Sell Multiplier"
        - ""
        - "&#00A4FCInformation"
        - "&fLevel: &#FCE300%level% &f/ &#FCE300%max_level%"
        - "&fMultiplier: &#00A4FC%multiplier%"
        - ""
        - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto View Progress"
    BOOK:
      SLOT: 15
      MATERIAL: ENCHANTED_BOOK
      TITLE: "&#FCE300&lBOOK"
      LORE:
        - "&7Sell Multiplier"
        - ""
        - "&#FCE300Information"
        - "&fLevel: &#FCE300%level% &f/ &#FCE300%max_level%"
        - "&fMultiplier: &#FCE300%multiplier%"
        - ""
        - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to View Progress"
    POTIONS:
      SLOT: 16
      MATERIAL: POTION
      TITLE: "&#A303F9&lPOTIONS"
      LORE:
        - "&7Sell Multiplier"
        - ""
        - "&#A303F9Information"
        - "&fLevel: &#FCE300%level% &f/ &#FCE300%max_level%"
        - "&fMultiplier: &#A303F9%multiplier%"
        - ""
        - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to View Progress"
    BLOCKS:
      SLOT: 17
      MATERIAL: BRICKS
      TITLE: "&7&lBLOCKS"
      LORE:
        - "&7Sell Multiplier"
        - ""
        - "&7Information"
        - "&fLevel: &#FCE300%level% &f/ &#FCE300%max_level%"
        - "&fMultiplier: &7%multiplier%"
        - ""
        - "&7▶ &7&l&nCLICK&r &7to View Progress"
```

## `economy/sellmulti/gui/progress.yml`

```yaml
PROGRESS-MENU:
  BUTTONS:
    BACK:
      SLOT: 45
      MATERIAL: RED_STAINED_GLASS_PANE
      TITLE: "&#FC0000&lBACK"
      LORE:
        - "&7Navigation"
        - ""
        - "&#FC0000Information"
        - "&fReturn to the"
        - "&fmultiplier overview."
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"
    LEVEL_COMPLETE:
      MATERIAL: LIME_STAINED_GLASS_PANE
      TITLE: "&#00FC00&lLEVEL %level% COMPLETE"
      LORE:
        - "&7Sell Multiplier Level"
        - ""
        - "&#00FC00Information"
        - "&fMultiplier: &#00FC00%multiplier%"
        - "&fThreshold: &#00FC00%threshold%"
        - ""
        - "&#00FC00✔ &fCompleted"
    LEVEL_ACTIVE:
      MATERIAL: YELLOW_STAINED_GLASS_PANE
      TITLE: "&#FCE300&lLEVEL %level%"
      LORE:
        - "&7Sell Multiplier Level"
        - ""
        - "&#FCE300Information"
        - "&fMultiplier on completion: &#FCE300%multiplier%"
        - "&fProgress: &#FCE300%progress% &7/ &#FCE300%threshold%"
        - "&fNeeded: &#FCE300%needed%"
        - "%bar%"
    LEVEL_LOCKED:
      MATERIAL: WHITE_STAINED_GLASS_PANE
      TITLE: "&7&lLEVEL %level%"
      LORE:
        - "&7Sell Multiplier Level"
        - ""
        - "&7Information"
        - "&fMultiplier on completion: &7%multiplier%"
        - "&fThreshold: &7%threshold%"
    PREV_PAGE:
      MATERIAL: ARROW
      TITLE: "&#FC0000&lPREVIOUS PAGE"
      LORE:
        - "&7Navigation"
        - ""
        - "&#FC0000Information"
        - "&fGo to the previous page"
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"
    NEXT_PAGE:
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

## `economy/sellmulti/gui/worth.yml`

```yaml

WORTH-MENU:

  TITLE: "&8%category%"

  ITEM-LORE:
    - "&7Server Worth"
    - ""
    - "&#00FC00Information"
    - "&fThis is the &#00FC00Price &fof this"
    - "&fitem when you &#00FC00sell &fit."
    - ""
    - "&#00FC00▶ &fWorth: &#00FC00%price%"
    - "&#00FC00▶ &fSellmulti &#FCE300%multiplier%&f: &#00FC00%sellmulti_price%"
  BUTTONS:
    BACK:
      MATERIAL: RED_STAINED_GLASS_PANE
      TITLE: "&#FC0000&lBACK"
      LORE:
        - "&7Navigation"
        - ""
        - "&#FC0000Information"
        - "&fReturn to the"
        - "&fcategory progress menu."
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"
    PREV_PAGE:
      MATERIAL: ARROW
      TITLE: "&#FC0000&lPREVIOUS PAGE"
      LORE:
        - "&7Navigation"
        - ""
        - "&#FC0000Information"
        - "&fGo to the previous page."
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"
    NEXT_PAGE:
      MATERIAL: ARROW
      TITLE: "&#00FC00&lNEXT PAGE"
      LORE:
        - "&7Navigation"
        - ""
        - "&#00FC00Information"
        - "&fGo to the next page."
        - ""
        - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Next Page"
```

## `economy/sellmulti/messages.yml`

```yaml
messages:
  level-up:  "&#00FC00&lSELL &r&7» &fYour &f%category% &fmultiplier reached Level &#FCE300%level%&f! Multiplier: &#00FC00%multiplier%&f."
  max-level: "&#00FC00&lSELL &r&7» &fYour &f%category% &fmultiplier is at max level! Multiplier: &#00FC00x3.0&f."
```

## `economy/sellmulti/sounds.yml`

```yaml
sounds:
  open:     "minecraft:ui.button.click|1.0|1.0"
  level-up: "minecraft:entity.player.levelup|1.0|1.0"
```

