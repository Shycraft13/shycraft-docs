# `economy/menus/guide.yml`

Location: `plugins/EconomyCore/economy/menus/guide.yml`

```yaml

command:
  - guide
  - help
title: "&8ɢᴜɪᴅᴇ"
rows: 3

items:

  economy:
    SLOT: 10
    MATERIAL: EMERALD
    TITLE: "&#00FC1C&lECONOMY"
    LORE:
      - "&7Guide"
      - ""
      - "&#00FC1CInformation"
      - "&fSell items to earn money."
      - "&fBuild farms and bases."
      - ""
      - "&#00FC1C▶ &#00FC1C&l&nCLICK&r &#00FC1Cto sell"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
      - "[close]"
      - "[command] sell"

  rules:
    SLOT: 11
    MATERIAL: BOOK
    TITLE: "&#00A4FC&lRULES"
    LORE:
      - "&7Guide"
      - ""
      - "&#00A4FCInformation"
      - "&fRead the server rules."
      - "&fAvoid punishments."
      - ""
      - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto view"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
      - "[open] rules"

  combat:
    SLOT: 12
    MATERIAL: DIAMOND_SWORD
    TITLE: "&#FC0000&lCOMBAT"
    LORE:
      - "&7Guide"
      - ""
      - "&#FC0000Information"
      - "&fFight other players."
      - "&fDominate in PvP battles."
      - ""
      - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to view"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
      - "[close]"
      - "[command] rtpqueue"

  shards:
    SLOT: 13
    MATERIAL: AMETHYST_SHARD
    TITLE: "&#9400FF&lSHARDS"
    LORE:
      - "&7Guide"
      - ""
      - "&#9400FFInformation"
      - "&fCollect shards."
      - "&fBuy spawners with them."
      - ""
      - "&#9400FF▶ &#9400FF&l&nCLICK&r &#9400FFto view"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
      - "[close]"
      - "[command] afk"

  teams:
    SLOT: 14
    MATERIAL: SHIELD
    TITLE: "&#00A4FC&lTEAMS"
    LORE:
      - "&7Guide"
      - ""
      - "&#00A4FCInformation"
      - "&fCreate or join teams."
      - "&fPlay together and win."
      - ""
      - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto open"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
      - "[close]"
      - "[command] team"

  rtp:
    SLOT: 15
    MATERIAL: COMPASS
    TITLE: "&#00FC1C&lRTP"
    LORE:
      - "&7Guide"
      - ""
      - "&#00FC1CInformation"
      - "&fTeleport to random areas."
      - "&fExplore the world."
      - ""
      - "&#00FC1C▶ &#00FC1C&l&nCLICK&r &#00FC1Cto teleport"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
      - "[close]"
      - "[command] rtp"

  store:
    SLOT: 16
    MATERIAL: CHEST_MINECART
    TITLE: "&#00FC00&lSTORE"
    LORE:
      - "&7Guide"
      - ""
      - "&#00FC00Information"
      - "&fSupport the server."
      - "&fBuy ranks and crate keys."
      - ""
      - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to view"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
      - "[open] store"
```
