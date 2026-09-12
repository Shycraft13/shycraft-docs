# Tags (`economy/tags/`)

Cosmetic name tags with a picker menu.

## `economy/tags/config.yml`

```yaml

default-sort: "OWNED"

search-min-length: 3

placeholder:
  format: " %tag%"

  empty: ""
```

## `economy/tags/gui/main.yml`

```yaml

gui:
  title: "&8ᴛᴀɢѕ"

  rows: 5

  items-per-page: 36

prev-page:
  SLOT: 36
  MATERIAL: ARROW
  TITLE: "&#FC0000&lPREVIOUS PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fGo back one page."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"

close:
  MATERIAL: RED_STAINED_GLASS_PANE
  TITLE: "&#FC0000&lCLOSE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fClose this menu."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Close"

sort:
  SLOT: 39
  MATERIAL: HOPPER
  TITLE: "&#FCE300&lSORTING"
  LORE-HEADER:
    - "&7Tag Order"
    - ""
    - "&7Current Selection"
  ACTIVE-PREFIX: "&#FCE300▶ &f"
  INACTIVE-PREFIX: "&7▶ &f"
  LORE-FOOTER:
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Change"

  MODES:
    OWNED: "Owned First"
    A_Z:   "A-Z"
    Z_A:   "Z-A"

clear:
  SLOT: 40
  MATERIAL: CHEST_MINECART
  TITLE: "&#FC0000&lCLEAR TAG"
  NONE: "&7None"
  LORE:
    - "&7Action"
    - ""
    - "&#FC0000Information"
    - "&fEquipped: %tag%"
    - "&fRemove the tag behind"
    - "&fyour name."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Clear"

search:
  SLOT: 41
  MATERIAL: OAK_SIGN
  TITLE: "&#00A4FC&lSEARCH"
  LORE:
    - "&7Tag Search"
    - ""
    - "&#00A4FCInformation"
    - "&fSearch for a tag"
    - "&fby name."
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Search"

search-active:
  MATERIAL: OAK_SIGN
  TITLE: "&#00FC99&lSEARCH"
  LORE:
    - "&7Tag Search"
    - ""
    - "&#00FC99Information"
    - "&fFiltering: &#00FC99%query%&f."
    - "&fType empty to clear."
    - ""
    - "&#00FC99▶ &#00FC99&l&nCLICK&r &#00FC99to Search Again"

next-page:
  SLOT: 44
  MATERIAL: ARROW
  TITLE: "&#00FC00&lNEXT PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#00FC00Information"
    - "&fGo forward one page."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Go Forward"

entry:
  TITLE: "%tag%"
  LORE-EQUIPPED:
    - "&7Tag"
    - ""
    - "&#00FC00Information"
    - "&fThis tag is equipped."
    - ""
    - "&#00FC00▶ &#00FC00&l&nEQUIPPED"
  LORE-OWNED:
    - "&7Tag"
    - ""
    - "&#00A4FCInformation"
    - "&fYou own this tag."
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Equip"
  LORE-LOCKED:
    - "&7Tag"
    - ""
    - "&#FC0000Information"
    - "&fYou do not own this tag."
    - "&fUnlock it on the store"
    - "&for with a rank."
    - ""
    - "&#FC0000▶ &#FC0000&l&nLOCKED"

FILLER:
  MATERIAL: AIR
  TITLE: " "
  LORE: []
```

## `economy/tags/messages.yml`

```yaml

messages:
  equipped: "&#00FC00&lTAG &r&7» &fEquipped %tag%&f."
  cleared: "&#00FC00&lTAG &r&7» &fCleared your tag."
  not-owned: "&cYou do not own that tag."
  already-equipped: "&cThat tag is already equipped."
  no-tag-equipped: "&cYou have no tag equipped."
  search-too-short: "&cMinimum %min% characters required."
  received: "&#00FC00&lTAG &r&7» &fYou received %tag%&f."
  lost: "&#FC0000&lTAG &r&7» &fYou lost %tag%&f."

manager:
  usage: "&#00A4FCUsage: &#FCE300/tagsmanager <create|delete|edit|give|remove> ..."
  usage-create: "&#00A4FCUsage: &#FCE300/tagsmanager create <name> [display]"
  usage-edit: "&#00A4FCUsage: &#FCE300/tagsmanager edit <name> <display>"
  usage-give: "&#00A4FCUsage: &#FCE300/tagsmanager give <player> <name>"
  usage-remove: "&#00A4FCUsage: &#FCE300/tagsmanager remove <player> <name>"
  invalid-name: "&cInvalid name. Letters, digits, _ and - only."
  exists: "&cThat tag already exists."
  not-found: "&cNo such tag."

  player-not-found: "&cNo player by that name has been on this server."
  created: "&#00FC00&lTAG &r&7» &fCreated %tag%&f."
  deleted: "&#FC0000&lTAG &r&7» &fDeleted the &#FCE300%name%&f tag."
  edited: "&#00FC00&lTAG &r&7» &fUpdated %tag%&f."
  given: "&#00FC00&lTAG &r&7» &fGave %tag% &fto &#00FC99%player%&f."
  removed: "&#FC0000&lTAG &r&7» &fRemoved %tag% &ffrom &#00FC99%player%&f."
  already-owned: "&cThat player already owns that tag."
  target-not-owned: "&cThat player does not own that tag."
```

## `economy/tags/sounds.yml`

```yaml

sounds:
  open: "minecraft:block.note_block.harp|0.7|1.6"
  equip: "minecraft:entity.player.levelup|0.7|1.6"
  clear: "minecraft:ui.button.click|0.7|1.0"
  error: "minecraft:entity.villager.no|0.7|1.0"
```

## `economy/tags/tags.yml`

```yaml

tags:

  berry:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FF7AC6&lB&#E96CD4&lE&#D35EE2&lR&#BD50F0&lR&#A742FF&lY&8]"
    PERMISSION: "economycore.tag.berry"

  seawater:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#00E5FF&lS&#00D1FF&lE&#00BCFF&lA&#00A8FF&lW&#0094FF&lA&#0080FF&lT&#006BFF&lE&#0057FF&lR&8]"
    PERMISSION: "economycore.tag.seawater"

  hacker:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#00FF6A&lH&#00E45F&lA&#00CA54&lC&#00AF49&lK&#00953E&lE&#007A33&lR&8]"
    PERMISSION: "economycore.tag.hacker"

  cat:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFB86B&lC&#FF8C65&lA&#FF5F5F&lT&8]"
    PERMISSION: "economycore.tag.cat"

  king:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFE259&lK&#FFCE56&lI&#FFBB54&lN&#FFA751&lG&8]"
    PERMISSION: "economycore.tag.king"

  ghost:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#E0E0E0&lG&#C3C3CC&lH&#A6A6B8&lO&#8888A3&lS&#6B6B8F&lT&8]"
    PERMISSION: "economycore.tag.ghost"

  lava:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFD000&lL&#FF9A00&lA&#FF6400&lV&#FF2E00&lA&8]"
    PERMISSION: "economycore.tag.lava"

  frost:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#E8F9FF&lF&#C0EBFF&lR&#99DDFF&lO&#71CFFF&lS&#4AC1FF&lT&8]"
    PERMISSION: "economycore.tag.frost"

  toxic:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#C6FF00&lT&#A3E900&lO&#7FD400&lX&#5CBE00&lI&#38A800&lC&8]"
    PERMISSION: "economycore.tag.toxic"

  void:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#B14AFF&lV&#8A35CE&lO&#631F9C&lI&#3C0A6B&lD&8]"
    PERMISSION: "economycore.tag.void"
  fire:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFF200&lF&#FFA100&lI&#FF5100&lR&#FF0000&lE&8]"
    PERMISSION: "economycore.tag.fire"

  ocean:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#8CF6FF&lO&#69C5F2&lC&#4694E6&lE&#2364D9&lA&#0033CC&lN&8]"
    PERMISSION: "economycore.tag.ocean"

  sunset:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFC24A&lS&#FFA454&lU&#FF875F&lN&#FF6969&lS&#FF4C74&lE&#FF2E7E&lT&8]"
    PERMISSION: "economycore.tag.sunset"

  nature:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#BFFF6B&lN&#9CE85F&lA&#79D053&lT&#55B946&lU&#32A13A&lR&#0F8A2E&lE&8]"
    PERMISSION: "economycore.tag.nature"

  blood:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FF4646&lB&#DA3434&lL&#B52323&lO&#901212&lO&#6B0000&lD&8]"
    PERMISSION: "economycore.tag.blood"

  royal:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFF3A0&lR&#F4DE7E&lO&#EACA5C&lY&#DFB539&lA&#D4A017&lL&8]"
    PERMISSION: "economycore.tag.royal"

  mythic:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FF6BF2&lM&#E156F5&lY&#C440F7&lT&#A62BFA&lH&#8915FC&lI&#6B00FF&lC&8]"
    PERMISSION: "economycore.tag.mythic"

  legend:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFE873&lL&#FFD25C&lE&#FFBC45&lG&#FFA62E&lE&#FF9017&lN&#FF7A00&lD&8]"
    PERMISSION: "economycore.tag.legend"

  demon:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FF3B3B&lD&#CE2C39&lE&#9D1E37&lM&#6C0F35&lO&#3B0033&lN&8]"
    PERMISSION: "economycore.tag.demon"

  angel:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFFFFF&lA&#FFF5DA&lN&#FFECB5&lG&#FFE290&lE&#FFD86B&lL&8]"
    PERMISSION: "economycore.tag.angel"

  storm:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#D9E6FF&lS&#B2BFFF&lT&#8A98FF&lO&#6272FF&lR&#3B4BFF&lM&8]"
    PERMISSION: "economycore.tag.storm"

  shadow:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#9B8BC4&lS&#8575AB&lH&#6E5E91&lA&#584878&lD&#41315E&lO&#2B1B45&lW&8]"
    PERMISSION: "economycore.tag.shadow"

  neon:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#39FF14&lN&#26F562&lE&#13EAB1&lO&#00E0FF&lN&8]"
    PERMISSION: "economycore.tag.neon"

  candy:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFB3E6&lC&#FF9AD2&lA&#FF80BD&lN&#FF66A8&lD&#FF4D94&lY&8]"
    PERMISSION: "economycore.tag.candy"

  gold:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFF6B0&lG&#F5DA75&lO&#EABE3B&lL&#E0A200&lD&8]"
    PERMISSION: "economycore.tag.gold"

  emerald:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#8CFFB0&lE&#75F0A0&lM&#5DE18F&lE&#46D27E&lR&#2FC26E&lA&#17B35E&lL&#00A44D&lD&8]"
    PERMISSION: "economycore.tag.emerald"

  diamond:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#B9F7FF&lD&#A1EFFA&lI&#89E7F5&lA&#72E0F0&lM&#5AD8EA&lO&#42D0E5&lN&#2AC8E0&lD&8]"
    PERMISSION: "economycore.tag.diamond"

  ruby:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FF8080&lR&#EB555F&lU&#D82B3E&lB&#C4001D&lY&8]"
    PERMISSION: "economycore.tag.ruby"

  phoenix:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFE066&lP&#FFC355&lH&#FFA644&lO&#FF8A33&lE&#FF6D22&lN&#FF5011&lI&#FF3300&lX&8]"
    PERMISSION: "economycore.tag.phoenix"

  venom:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#D6FF4D&lV&#A8E23A&lE&#7AC426&lN&#4DA713&lO&#1F8A00&lM&8]"
    PERMISSION: "economycore.tag.venom"

  arctic:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFFFFF&lA&#DFF6FF&lR&#BFECFF&lC&#9FE3FF&lT&#7FD9FF&lI&#5FD0FF&lC&8]"
    PERMISSION: "economycore.tag.arctic"

  magma:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFA24A&lM&#E27D38&lA&#C45825&lG&#A73412&lM&#8A0F00&lA&8]"
    PERMISSION: "economycore.tag.magma"

  galaxy:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#7A4DFF&lG&#954DF6&lA&#AF4DED&lL&#CA4DE4&lA&#E44DDB&lX&#FF4DD2&lY&8]"
    PERMISSION: "economycore.tag.galaxy"

  pirate:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#E0C68A&lP&#C9AD75&lI&#B1945F&lR&#9A7C4A&lA&#826334&lT&#6B4A1F&lE&8]"
    PERMISSION: "economycore.tag.pirate"

  ninja:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#8A8A8A&lN&#6E6E6E&lI&#525252&lN&#363636&lJ&#1A1A1A&lA&8]"
    PERMISSION: "economycore.tag.ninja"

  dragon:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#B84DFF&lD&#9C3EDD&lR&#812EBC&lA&#651F9A&lG&#4A0F79&lO&#2E0057&lN&8]"
    PERMISSION: "economycore.tag.dragon"

  sniper:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#A8FF8A&lS&#8DE16E&lN&#71C453&lI&#56A637&lP&#3A891C&lE&#1F6B00&lR&8]"
    PERMISSION: "economycore.tag.sniper"

  titan:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#D6D6D6&lT&#BBBBBB&lI&#A0A0A0&lT&#868686&lA&#6B6B6B&lN&8]"
    PERMISSION: "economycore.tag.titan"

  rainbow:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FF0000&lR&#FF7F00&lA&#FFD500&lI&#4AFF00&lN&#00D5FF&lB&#4A4AFF&lO&#B14AFF&lW&8]"
    PERMISSION: "economycore.tag.rainbow"

  chill:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#C4FFFB&lC&#A6E6FC&lH&#87CDFD&lI&#68B4FE&lL&#4A9BFF&lL&8]"
    PERMISSION: "economycore.tag.chill"

  hunter:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#C4A46B&lH&#B08F59&lU&#9B7A46&lN&#876434&lT&#724F21&lE&#5E3A0F&lR&8]"
    PERMISSION: "economycore.tag.hunter"

  wither:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#5E5E5E&lW&#4E4E4E&lI&#3E3E3E&lT&#2F2F2F&lH&#1F1F1F&lE&#0F0F0F&lR&8]"
    PERMISSION: "economycore.tag.wither"

  nether:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FF7A6B&lN&#E86859&lE&#D05646&lT&#B94334&lH&#A13121&lE&#8A1F0F&lR&8]"
    PERMISSION: "economycore.tag.nether"

  ender:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#6BFFD6&lE&#54D7B3&lN&#3DAE90&lD&#26866D&lE&#0F5E4A&lR&8]"
    PERMISSION: "economycore.tag.ender"

  sakura:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#FFD6E8&lS&#FFC1DB&lA&#FFABCE&lK&#FF96C2&lU&#FF80B5&lR&#FF6BA8&lA&8]"
    PERMISSION: "economycore.tag.sakura"

  cyber:
    MATERIAL: NAME_TAG
    DISPLAY: "&8[&#00FFD1&lC&#00D9DC&lY&#00B2E8&lB&#008CF4&lE&#0066FF&lR&8]"
    PERMISSION: "economycore.tag.cyber"
```

