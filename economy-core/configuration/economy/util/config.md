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
  blocked-materials:
    - SPAWNER
    - TRIAL_SPAWNER
  block-mythic-tools: true
  block-styled-names: true
  block-custom-model-data: false

messages:
  no-permission: "&cNo permission."
  players-only: "&cOnly players can use this command."
  gui-busy: "&cClose your current screen first."
  glow-enabled: "&#00A4FC&lGLOW &r&7» &fYou are now glowing."
  glow-disabled: "&#00A4FC&lGLOW &r&7» &fYou are no longer glowing."
  glow-other-enabled: "&#00A4FC&lGLOW &r&7» &#00FC99%player% &fis now glowing."
  glow-other-disabled: "&#00A4FC&lGLOW &r&7» &#00FC99%player% &fis no longer glowing."
  glow-player-not-found: "&cPlayer %player% has never joined."
  sign-success: "&#00A4FC&lSIGN &r&7» &fItem signed."
  sign-no-item: "&cHold an item to sign it."
  sign-not-allowed: "&cThis item cannot be signed."
  sign-already: "&cYou already signed this item."
  sign-limit: "&cThis item already has %max% signatures."
  sign-cooldown: "&cYou can sign again in %time%."
  sign-amount: "&cYou can only sign a single item. Split the stack first."
  sign-message-disabled: "&cYou cannot add a message to a signature."
  sign-message-length: "&cThe message may be at most %max% characters."
  sign-message-no-colors: "&cColor codes are not allowed in a signature message."
  sign-message-tag-forbidden: "&cThe <%tag%> tag is not allowed in a signature message."
  sign-message-blocked: "&cThat message contains a blocked word."
  rename-success: "&#00A4FC&lRENAME &r&7» &fItem renamed."
  rename-no-item: "&cHold an item to rename it."
  rename-not-allowed: "&cThis item cannot be renamed."
  rename-cooldown: "&cYou can rename again in %time%."
  rename-no-colors: "&cColor codes are not allowed in item names."
  rename-tag-forbidden: "&cThe <%tag%> tag is not allowed in an item name. Only colours and gradients are."
  rename-length: "&cItem names must be 1-%max% characters."
  rename-blocked: "&cThat name contains a blocked word."
  nightvision-enabled: "&#00A4FC&lNIGHT VISION &r&7» &fNight vision is now on."
  nightvision-disabled: "&#00A4FC&lNIGHT VISION &r&7» &fNight vision is now off."
```

## Protecting plugin items from `/rename`

`/rename` refuses items that belong to a plugin instead of to the player, so a rename
cannot destroy an item's identity or be silently undone the next time the owning plugin
rewrites that item. All four checks are independent and share one message,
`rename-not-allowed`. They run before the cooldown, so a player holding a protected item
is told the item is the problem instead of being sent away with a wait time.

| Key | Default | What it refuses |
| --- | --- | --- |
| `blocked-materials` | `SPAWNER`, `TRIAL_SPAWNER` | Item types that can never be renamed. Add the materials of your own custom items here. An unknown material name is logged on startup and skipped, it never disables the command. |
| `block-mythic-tools` | `true` | Mythic tools created with `/mythictool`. |
| `block-styled-names` | `true` | Any item whose current name already carries a colour, a format code or a click/hover action. |
| `block-custom-model-data` | `false` | Items with custom model data. Off by default, because it also catches purely cosmetic resource-pack items. |

`block-styled-names` is the general rule for third-party custom items: a vanilla item has
no name at all and an anvil-renamed item has a plain white one, while a custom item from
another plugin is almost always coloured. Any colour, any formatting that is actually
switched on, or any click or hover action counts as "not the player's item", including
inside a gradient.

An item that was renamed with `/rename` itself stays renamable. With
`allow-color-codes: true` a player would otherwise lock themselves out of their own item
the moment they gave it a colour.
