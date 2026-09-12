# RTP Queue (`economy/rtpqueue/`)

Queued RTP so multiple players can rejoin the search safely.

## `economy/rtpqueue/config.yml`

```yaml

countdown-seconds: 5

search-attempts: 15

WORLD-SETTINGS:
  world:
    MAX-RADIUS: 5000
    MIN-RADIUS: 500
    CENTER-X: 0
    CENTER-Z: 0
  world_nether:
    MAX-RADIUS: 500
    MIN-RADIUS: 50
    CENTER-X: 0
    CENTER-Z: 0
  world_the_end:
    MAX-RADIUS: 2000
    MIN-RADIUS: 150
    CENTER-X: 0
    CENTER-Z: 0
```

## `economy/rtpqueue/gui/mainmenu.yml`

```yaml
GUI:
  TITLE: "&8ʀᴛᴘ ǫᴜᴇᴜᴇ"
  SIZE: 27

  CANCEL:
    SLOT: 10
    MATERIAL: RED_STAINED_GLASS_PANE
    TITLE: "&#FC0000&lCANCEL"
    LORE:
      - "&7Queue"
      - ""
      - "&#FC0000Information"
      - "&fClose this menu"
      - ""
      - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to close"

  WORLD:
    SLOT: 12

    MATERIAL: GRASS_BLOCK
    TITLE: "&#00A4FC&lWORLD"
    LORE:
      - "&7Queue"
      - ""
      - "&#00A4FCInformation"
      - "&fChoose which world"
      - "&fto get teleported to"
      - ""
      - "&#00A4FC▶ &fSelected: &#00A4FC%world%"
      - ""
      - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto change world"

  WORLD-MATERIALS:
    world: GRASS_BLOCK
    world_nether: NETHERRACK
    world_the_end: END_STONE

  INFO:
    SLOT: 13
    MATERIAL: CLOCK
    TITLE: "&#FCE300&lQUEUE INFO"
    LORE:
      - "&7Queue"
      - ""
      - "&#FCE300Information"
      - "&fPlayers currently"
      - "&fwaiting for a match"
      - ""
      - "&#FCE300▶ &fIn queue: &#FCE300%queued%"
      - "&#FCE300▶ &fWorld: &#FCE300%world%"

  PING:
    SLOT: 14
    MATERIAL: FEATHER
    TITLE: "&#00A4FC&lYOUR PING"
    LORE:
      - "&7Connection"
      - ""
      - "&#00A4FCInformation"
      - "&fYour latency to"
      - "&fthe server"
      - ""
      - "&#00A4FC▶ &fPing: &#00A4FC%ping% ms"

  CONFIRM:
    SLOT: 16
    MATERIAL: LIME_STAINED_GLASS_PANE
    TITLE: "&#00FC00&lJOIN QUEUE"
    LORE:
      - "&7Queue"
      - ""
      - "&#00FC00Information"
      - "&fJoin the 1v1 queue"
      - "&ffor &#00FC00%world%"
      - ""
      - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to confirm"
```

## `economy/rtpqueue/messages.yml`

```yaml
messages:

  broadcast-joined: "&#00A4FC&lRTPQUEUE &r&7» &f%player% &7joined the queue for &#00A4FC%world%&7."
  broadcast-hover: "&7Click to duel &#00A4FC%player%&7."

  searching: "&7Searching for an opponent in &#00A4FC%world%&7..."

  joined: "&#00A4FC&lRTPQUEUE &r&7» &fYou joined the queue for &#00A4FC%world%&7."

  left: "&#00A4FC&lRTPQUEUE &r&7» &fYou left the queue."

  matched: "&#00A4FC&lRTPQUEUE &r&7» &fOpponent &#00A4FC%opponent% &ffound&7."

  countdown: "&7Teleporting in &#00A4FC%time%s&7..."

  teleported: "&7Teleported!"

  already-queued: "&#FC0000You are already in the queue."
  not-queued: "&#FC0000You are not in the queue."
  world-not-found: "&#FC0000That world is not available."
  players-only: "&#FC0000Players only."
```

## `economy/rtpqueue/sounds.yml`

```yaml
sounds:

  click: "minecraft:ui.button.click|1.0|1.0"

  join: "minecraft:block.note_block.pling|1.0|1.2"

  leave: "minecraft:block.note_block.bass|1.0|0.8"

  countdown: "minecraft:block.note_block.hat|0.4|1.0"

  teleport: "minecraft:entity.experience_orb.pickup|1.0|1.0"
```

