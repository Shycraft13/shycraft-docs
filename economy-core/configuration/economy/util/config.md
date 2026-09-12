# `economy/util/config.yml`

Location: `plugins/EconomyCore/economy/util/config.yml`

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
