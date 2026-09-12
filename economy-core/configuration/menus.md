# Custom Menus (`economy/menus/`)

Custom clickable menus. Ships with discord, guide, media, rules and store.

## `economy/menus/discord.yml`

```yaml

command:
  - discord
title: "&8ᴅɪꜱᴄᴏʀᴅ"
rows: 3
open-sound: "minecraft:block.note_block.pling|0.7|1.2"

items:

  info:
    SLOT: 13
    MATERIAL: LIGHT_BLUE_CANDLE
    TITLE: "&#5865F2&lDISCORD"
    LORE:
      - "&7Community"
      - ""
      - "&#5865F2Information"
      - "&fJoin our &#5865F2Discord &fto chat with"
      - "&fthe community and get support."
      - ""
      - "&#5865F2▶ &#5865F2&l&nCLICK&r &#5865F2to get the link"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
      - "[close]"
      - "[msg]            &#5865F2&lDISCORD"
      - "[msg] "
      - "[msg] &fJoin our &#5865F2Discord &fto chat with the community."
      - "[msg] &fGet &#5865F2support &fand hear about &#5865F2events &ffirst."
      - "[msg] &fEveryone is welcome, come say hi!"
      - "[msg] "
      - "[msg]         &#5865F2<click:open_url:'https://discord.gg/yourserver'><hover:show_text:'&fOpen &#5865F2discord.gg/yourserver'>▶ discord.gg/yourserver ◀</hover></click>  "
```

## `economy/menus/guide.yml`

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

## `economy/menus/media.yml`

```yaml

command:
  - media
title: "&8ᴍᴇᴅɪᴀ"
rows: 3
open-sound: "minecraft:block.note_block.pling|0.7|1.2"

items:

  info:
    SLOT: 13
    MATERIAL: MAGENTA_CANDLE
    TITLE: "&#FC00E3&lMEDIA RANK"
    LORE:
      - "&7Creator"
      - ""
      - "&#FC00E3Requirements &7(only one needed)"
      - "&#FC00E3&l| &r&f15 average viewers on stream"
      - "&#FC00E3&l| &r&f5k views on a YouTube video"
      - "&#FC00E3&l| &r&f35k views on a TikTok"
      - "&#FC00E3&l| &r&f25k views on a YouTube Short"
      - ""
      - "&#FC00E3Reminders"
      - "&#FC00E3&l| &r&fMust have the IP on screen"
      - "&#FC00E3&l| &r&fMust be from the new season"
      - "&#FC00E3&l| &r&fOpen a ticket in Discord for the rank"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
```

## `economy/menus/rules.yml`

```yaml

command:
  - rules
title: "&8ʀᴜʟᴇꜱ"
rows: 3

items:

  server:
    SLOT: 11
    MATERIAL: BOOK
    TITLE: "&#00A4FC&lSERVER RULES"
    LORE:
      - "&7Rules"
      - ""
      - "&#00A4FCInformation"
      - "&#00A4FC&l| &r&fNo Hacked Clients"
      - "&#00A4FC&l| &r&fNo Movement Mods"
      - "&#00A4FC&l| &r&fNo Inventory Mods"
      - "&#00A4FC&l| &r&fNo Health Indicators"
      - "&#00A4FC&l| &r&fNo Radar"
      - "&#00A4FC&l| &r&fNo Freecam"
      - "&#00A4FC&l| &r&fNo Auto Place"
      - "&#00A4FC&l| &r&fNo Easy Place"
      - "&#00A4FC&l| &r&fNo Auto Clicker"
      - "&#00A4FC&l| &r&fNo Macros or Scripts"
      - "&#00A4FC&l| &r&fNo Bug Abusing"
      - "&#00A4FC&l| &r&fNo Duping Methods"
      - "&#00A4FC&l| &r&fNo IRL Trading"
      - "&#00A4FC&l| &r&fNo Cross-Server Trading"
      - "&#00A4FC&l| &r&fNo Seed Finding/Using"
      - "&#00A4FC&l| &r&fMax 5 Accounts per player"
      - "&#00A4FC&l| &r&fNo Mouse Tweaks / Scrollers"
      - "&#00A4FC&l| &r&fNo Crafting Modifications"
      - "&#00A4FC&l| &r&fNo Staff Impersonation"
      - ""
      - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto view"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
      - "[close]"
      - "[msg]            &#00A4FC&lSERVER RULES"
      - "[msg] "
      - "[msg] &fPlay fair, no &#00A4FCcheating&f. &#00A4FCGriefing &fand &#00A4FCscamming &fare allowed."
      - "[msg] &fUse only the mods allowed above."
      - "[msg] &fBreaking these rules leads to &#00A4FCpunishment&f."
      - "[msg] "
      - "[msg]              &#00A4FC▶ /rules ◀  "

  chat:
    SLOT: 15
    MATERIAL: BOOK
    TITLE: "&#00A4FC&lCHAT RULES"
    LORE:
      - "&7Rules"
      - ""
      - "&#00A4FCInformation"
      - "&#00A4FC&l| &r&fNo Spamming or forcing spam"
      - "&#00A4FC&l| &r&fNo Harassing"
      - "&#00A4FC&l| &r&fNo Advertising or Promotion"
      - "&#00A4FC&l| &r&fNo Discrimination / Hate Speech"
      - "&#00A4FC&l| &r&fNo Death Threats"
      - "&#00A4FC&l| &r&fNo Sharing Private Info"
      - "&#00A4FC&l| &r&fNo Impersonating others"
      - "&#00A4FC&l| &r&fNo Ban Evasion"
      - "&#00A4FC&l| &r&fNo Lying to Staff"
      - ""
      - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto view"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
      - "[close]"
      - "[msg]             &#00A4FC&lCHAT RULES"
      - "[msg] "
      - "[msg] &fKeep chat &#00A4FCfriendly &fand &#00A4FCrespectful &fto everyone."
      - "[msg] &fNo &#00A4FCspam&f, &#00A4FCharassment &for &#00A4FCadvertising&f."
      - "[msg] &fBreaking these rules leads to &#00A4FCpunishment&f."
      - "[msg] "
      - "[msg]              &#00A4FC▶ /rules ◀  "
```

## `economy/menus/store.yml`

```yaml

command:
  - store
title: "&8ꜱᴛᴏʀᴇ"
rows: 3
open-sound: "minecraft:block.note_block.pling|0.7|1.2"

items:

  info:
    SLOT: 13
    MATERIAL: LIGHT_BLUE_CANDLE
    TITLE: "&#00FC00&lSTORE"
    LORE:
      - "&7Support"
      - ""
      - "&#00FC00Information"
      - "&fGrab &#00FC00ranks&f, &#00FC00keys &fand more."
      - "&fEvery purchase keeps us &#00FC00online&f."
      - ""
      - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to get the link"
    ACTIONS:
      - "[sound] minecraft:ui.button.click volume=1 pitch=1"
      - "[close]"
      - "[msg]              &#00FC00&lSTORE"
      - "[msg] "
      - "[msg] &fSupport the server and grab &#00FC00ranks&f, &#00FC00keys &fand more."
      - "[msg] &fEvery purchase keeps the server &#00FC00online&f."
      - "[msg] &fThank you for helping the community grow."
      - "[msg] "
      - "[msg]         &#00FC00▶ store.yourserver.net ◀  "
```

