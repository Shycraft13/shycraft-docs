# `economy/tpa/gui/confirm.yml`

Location: `plugins/EconomyCore/economy/tpa/gui/confirm.yml`

```yaml
TPA-CONFIRM-MENU:
  TPA-TITLE: "&8ꜱᴇɴᴅ ᴛᴘᴀ"
  TPAHERE-TITLE: "&8ꜱᴇɴᴅ ᴛᴘᴀ ʜᴇʀᴇ"
  SIZE: 27

  BUTTONS:
    CANCEL:
      MATERIAL: RED_STAINED_GLASS_PANE
      TITLE: "&#FC0000&lCANCEL"
      SLOT: 10
      LORE:
        - "&7Cancel"
        - ""
        - "&#FC0000Information"
        - "&fCancel this request"
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Cancel"

    CONFIRM:
      MATERIAL: LIME_STAINED_GLASS_PANE
      TITLE: "&#00FC00&lSEND"
      SLOT: 16
      LORE:
        - "&7Send Request"
        - ""
        - "&#00FC00Information"
        - "&fSend teleport request to"
        - "&#00FC99%player%"
        - ""
        - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Send"

    PLAYER:
      MATERIAL: PLAYER_HEAD
      TITLE: "&#00FC99&l%player%"
      SLOT: 13
      LORE:
        - "&7Target Player"
        - ""
        - "&#00FC99Information"
        - "&fName: &#00FC99%player%"

    LOCATION:
      TITLE: "&#00FC00&lLOCATION"
      MATERIAL: GRASS_BLOCK
      SLOT: 12

      WORLD-BLOCKS:
        world: GRASS_BLOCK
        world_nether: NETHERRACK
        world_the_end: END_STONE

      LORE:
        - "&7Current World"
        - ""
        - "&#00FC00Information"
        - "&f%world%"

    REGION:
      TITLE: "&#00A4FC&lCONNECTION"
      MATERIAL: FEATHER
      SLOT: 14
      LORE:
        - "&7Ping"
        - ""
        - "&#00A4FCInformation"
        - "&fPing: &#00A4FC%ping%ms"
```
