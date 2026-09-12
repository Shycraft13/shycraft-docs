# Leaderboard (`economy/leaderboard/`)

Category menus for balance, kills, playtime, shards and bounties.

## `economy/leaderboard/gui/category.yml`

```yaml
gui:
  title: "&8ʟᴇᴀᴅᴇʀʙᴏᴀʀᴅѕ"

shards:
  SLOT: 12
  MATERIAL: AMETHYST_SHARD
  COLOR: "&#A303F9"
  TITLE: "&#A303F9&lSHARDS"
  LORE:
    - "&7Top Shards"
    - ""
    - "&#A303F9Information"
    - "&fView players with"
    - "&fthe most shards"
    - ""
    - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to View"

balance:
  SLOT: 11
  MATERIAL: EMERALD
  COLOR: "&#00FC00"
  TITLE: "&#00FC00&lBALANCE"
  LORE:
    - "&7Top Balance"
    - ""
    - "&#00FC00Information"
    - "&fView the richest"
    - "&fplayers on the server"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to View"

playtime:
  SLOT: 15
  MATERIAL: CLOCK
  COLOR: "&#FCE300"
  TITLE: "&#FCE300&lPLAYTIME"
  LORE:
    - "&7Top Playtime"
    - ""
    - "&#FCE300Information"
    - "&fView players with"
    - "&fmost time played"
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to View"

kills:
  SLOT: 13
  MATERIAL: IRON_SWORD
  COLOR: "&#FC0000"
  TITLE: "&#FC0000&lKILLS"
  LORE:
    - "&7Top Kills"
    - ""
    - "&#FC0000Information"
    - "&fView the most"
    - "&fdeadly players"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to View"

deaths:
  SLOT: 14
  MATERIAL: SKELETON_SKULL
  COLOR: "&#F97603"
  TITLE: "&#F97603&lDEATHS"
  LORE:
    - "&7Top Deaths"
    - ""
    - "&#F97603Information"
    - "&fView players with"
    - "&fthe most deaths"
    - ""
    - "&#F97603▶ &#F97603&l&nCLICK&r &#F97603to View"
```

## `economy/leaderboard/gui/leaderboard.yml`

```yaml
gui:
  title: "&8ʟᴇᴀᴅᴇʀʙᴏᴀʀᴅ %type%"

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
  MATERIAL: PLAYER_HEAD
  TITLE: "%color%&lREFRESH"
  LORE:
    - "&7Your Position"
    - ""
    - "%color%Information"
    - "&fPosition: %color%%position%"
    - "&f%type%: %color%%value%"
    - ""
    - "%color%▶ %color%&l&nCLICK&r %color%to Refresh"

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
  TITLE: "%color%#%position% %name%"
  LORE:
    - "&7%type%: %color%%value%"

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

## `economy/leaderboard/sounds.yml`

```yaml
sounds:
  open: "minecraft:ui.button.click|1.0|1.0"
```

