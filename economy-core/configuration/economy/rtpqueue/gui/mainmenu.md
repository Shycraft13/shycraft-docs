# `economy/rtpqueue/gui/mainmenu.yml`

Location: `plugins/EconomyCore/economy/rtpqueue/gui/mainmenu.yml`

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
