# Utility Commands (`economy/util/`)

/enderchest, /craft, /anvil, /grindstone, /loom, /cartography, /smithing, /stonecutter, /glow.

## `economy/util/config.yml`

```yaml

utilities:
  enderchest:
    enabled: true
    permission: "economy.util.enderchest"
    commands: ["enderchest", "ec", "ender"]

  workbench:
    enabled: true
    permission: "economy.util.workbench"
    commands: ["craft", "workbench"]

  anvil:
    enabled: true
    permission: "economy.util.anvil"
    commands: ["anvil"]

  grindstone:
    enabled: true
    permission: "economy.util.grindstone"
    commands: ["grindstone", "grind"]

  loom:
    enabled: true
    permission: "economy.util.loom"
    commands: ["loom"]

  cartography:
    enabled: true
    permission: "economy.util.cartography"
    commands: ["cartography", "carto"]

  smithing:
    enabled: true
    permission: "economy.util.smithing"
    commands: ["smithing"]

  stonecutter:
    enabled: true
    permission: "economy.util.stonecutter"
    commands: ["stonecutter"]

glow:
  enabled: true
  permission: "economy.glow.use"
  admin-permission: "economy.glow.others"
  commands: ["glow"]

messages:
  no-permission: "&#FC0000You don't have permission to use this."
  players-only: "&#FC0000Only players can use this command."
  gui-busy: "&#FC0000Close your current screen first."
  glow-enabled: "&#AAAAAAYou are now glowing."
  glow-disabled: "&#AAAAAAYou are no longer glowing."
  glow-other-enabled: "&#AAAAAA%player% is now glowing."
  glow-other-disabled: "&#AAAAAA%player% is no longer glowing."
  glow-usage: "&#FC0000Usage: /glow [player]"
  glow-player-not-found: "&#FC0000Player &f%player% &#FC0000has never joined."
```

## `economy/util/sounds.yml`

```yaml

sounds:
  enderchest:  "minecraft:block.ender_chest.open|1.0|1.0"
  workbench:   "minecraft:ui.button.click|0.6|1.2"
  anvil:       "minecraft:block.anvil.land|0.2|1.6"
  grindstone:  "minecraft:block.grindstone.use|0.5|1.0"
  loom:        "minecraft:ui.loom.select_pattern|0.8|1.0"
  cartography: "minecraft:ui.cartography_table.take_result|0.8|1.0"
  smithing:    "minecraft:block.smithing_table.use|0.8|1.0"
  stonecutter: "minecraft:ui.stonecutter.take_result|0.8|1.0"
  glow-on:     "minecraft:block.beacon.activate|0.6|1.6"
  glow-off:    "minecraft:block.beacon.deactivate|0.6|1.6"
```

