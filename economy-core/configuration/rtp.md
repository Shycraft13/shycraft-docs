# RTP (`economy/rtp/`)

Random teleport across configurable per-world zones.

## `economy/rtp/config.yml`

```yaml

search-attempts: 15

parallel-chunks: 8
teleport-delay: 5
default-cooldown: 10

WORLD-SETTINGS:
  world:
    MAX-RADIUS: 5000
    MIN-RADIUS: 500
    CENTER-X: 0
    CENTER-Z: 0
    COOLDOWN: 30
  world_nether:
    MAX-RADIUS: 500
    MIN-RADIUS: 50
    CENTER-X: 0
    CENTER-Z: 0
    COOLDOWN: 30
  world_the_end:
    MAX-RADIUS: 2000
    MIN-RADIUS: 150
    CENTER-X: 0
    CENTER-Z: 0
    COOLDOWN: 30
```

## `economy/rtp/gui/selector.yml`

```yaml
GUI:
  TITLE: "&8ᴄʜᴏᴏꜱᴇ ᴅɪᴍᴇɴꜱɪᴏɴ"
  SIZE: 27

  DIMENSIONS:
    OVERWORLD:
      TITLE: "&#00FC00&lOVERWORLD"
      MATERIAL: GRASS_BLOCK
      SLOT: 11
      ENABLED: true
      WORLD: "world"
      LORE:
        - "&7Overworld"
        - ""
        - "&#00FC00Information"
        - "&fTeleport to a random"
        - "&flocation in the Overworld"
        - ""
        - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Teleport"

    NETHER:
      TITLE: "&#FC0000&lNETHER"
      MATERIAL: NETHERRACK
      SLOT: 13
      ENABLED: true
      WORLD: "world_nether"
      LORE:
        - "&7Nether"
        - ""
        - "&#FC0000Information"
        - "&fTeleport to a random"
        - "&flocation in the Nether"
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Teleport"

    END:
      TITLE: "&#CC99FF&lTHE END"
      MATERIAL: END_STONE
      SLOT: 15
      ENABLED: true
      WORLD: "world_the_end"
      LORE:
        - "&7The End"
        - ""
        - "&#CC99FFInformation"
        - "&fTeleport to a random"
        - "&flocation in The End"
        - ""
        - "&#CC99FF▶ &#CC99FF&l&nCLICK&r &#CC99FFto Teleport"
```

## `economy/rtp/messages.yml`

```yaml
messages:
  searching:       "&7Searching for a safe location..."
  success:         "&7Arrived at a random location!"
  failed:          "&cCould not find a safe location."
  cooldown:        "&7Please wait &#FCE300%time%s&7."
  world-disabled:  "&cRTP is disabled in this world."
  world-not-found: "&cWorld not found."
  already-teleporting: "&cYou are already teleporting."
```

## `economy/rtp/sounds.yml`

```yaml
sounds:
  click: "minecraft:ui.button.click|1.0|1.0"
  success: "minecraft:entity.experience_orb.pickup|1.0|1.0"
```

