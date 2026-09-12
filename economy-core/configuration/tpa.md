# TPA (`economy/tpa/`)

/tpa, /tpahere, /back and the confirmation menu.

## `economy/tpa/config.yml`

```yaml
teleport-delay: 5
```

## `economy/tpa/gui/confirm.yml`

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

## `economy/tpa/messages.yml`

```yaml
messages:
  request-sent:        "&#00A4FC&lTPA &r&7» &fRequest sent to &#00FC99%player%&f."
  request-received:    "&#00A4FC&lTPA &r&7» &#00FC99%player% &fwants to teleport to you."
  tpahere-received:    "&#00A4FC&lTPA &r&7» &#00FC99%player% &fwants you to teleport to them."
  accepted-requester:  "&#00A4FC&lTPA &r&7» &#00FC99%accepter% &faccepted your request."
  accepted-accepter:   "&#00A4FC&lTPA &r&7» &fAccepted &#00FC99%from%&f's request."
  denied:              "&#00A4FC&lTPA &r&7» &fRequest denied."
  no-request:          "&cNo pending teleport requests."
  player-not-found:    "&cPlayer not found or not online."
  already-pending:     "&cAlready have a pending request to &#00FC99%player%&c."
  accept-text:         "&#00FC00[ACCEPT]"
  accept-hover:        "&7Click to accept the request"
  deny-text:           "&#FC0000[DENY]"
  deny-hover:          "&7Click to deny the request"

  auto-enabled:        "&#00A4FC&lTPA &r&7» &fAuto-accept &#00FC00enabled&f."
  auto-disabled:       "&#00A4FC&lTPA &r&7» &fAuto-accept &#FC0000disabled&f."

  auto-actionbar:      "&7Accepting all teleport requests"
```

## `economy/tpa/sounds.yml`

```yaml
sounds:
  click: "minecraft:ui.button.click|1.0|1.0"
  request-sent: "minecraft:block.note_block.bit|1.0|1.0"
  request-received: "minecraft:block.note_block.chime|1.0|1.0"
  accepted: "minecraft:entity.experience_orb.pickup|1.0|1.0"
  denied: "minecraft:entity.villager.no|1.0|1.0"
```

