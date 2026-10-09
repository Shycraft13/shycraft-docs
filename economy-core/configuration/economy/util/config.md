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

nightvision:
  enabled: true
  permission: "economy.util.nightvision"
  commands: ["nightvision", "nv"]

sign:
  enabled: true
  permission: "economy.util.sign"
  commands: ["sign"]
  cooldown-seconds: 600
  max-signatures: 10
  format:
    - ""
    - "&7Signed by &#00FC99%player%"
  only-single-item: false
  message:
    enabled: true
    max-length: 32
    allow-color-codes: false
    format:
      - "&7» &f%message%"

rename:
  enabled: true
  permission: "economy.util.rename"
  commands: ["rename"]
  max-length: 25
  allow-color-codes: false
  cooldown-seconds: 60

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
  sign-success: "&7Item signed."
  sign-no-item: "&cHold an item to sign it."
  sign-not-allowed: "&cThis item cannot be signed."
  sign-already: "&cYou already signed this item."
  sign-limit: "&cThis item already has %max% signatures."
  sign-cooldown: "&cYou can sign again in %time%."
  sign-amount: "&cYou can only sign a single item. Split the stack first."
  sign-message-disabled: "&cYou cannot add a message to a signature."
  sign-message-length: "&cThe message may be at most %max% characters."
  sign-message-no-colors: "&cColor codes are not allowed in a signature message."
  sign-message-tag-forbidden: "&cThe &f<%tag%> &ctag is not allowed in a signature message."
  sign-message-blocked: "&cThat message contains a blocked word."
  rename-success: "&7Item renamed."
  rename-usage: "&cUsage: /rename <name>"
  rename-no-item: "&cHold an item to rename it."
  rename-cooldown: "&cYou can rename again in %time%."
  rename-no-colors: "&cColor codes are not allowed in item names."
  rename-tag-forbidden: "&cThe &f<%tag%> &ctag is not allowed in an item name. Only colours and gradients are."
  rename-length: "&cItem names must be 1-%max% characters."
  rename-blocked: "&cThat name contains a blocked word."
  nightvision-enabled: "&7Night vision is now on."
  nightvision-disabled: "&7Night vision is now off."
```
