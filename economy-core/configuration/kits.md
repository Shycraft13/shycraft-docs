# Kits (`economy/kits/`)

Kits, per-kit cooldowns, in-game editor and a bundled starter kit.

## `economy/kits/config.yml`

```yaml

kits:

  first-join-kit: starter

  default-cooldown: 1d

  default-permission-required: true

  layout-requires-permission: false
```

## `economy/kits/gui/editor.yml`

```yaml

TITLE: "&8ᴇᴅɪᴛ %kit%"

DIVIDER:
  MATERIAL: GRAY_STAINED_GLASS_PANE
  TITLE: " "

SAVE:
  MATERIAL: LIME_STAINED_GLASS_PANE
  TITLE: "&#00FC00&lSAVE"
  LORE:
    - "&7Action"
    - ""
    - "&#00FC00Information"
    - "&fWrite this layout"
    - "&fto the kit"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Save"
```

## `economy/kits/gui/main.yml`

```yaml
TITLE: "&8ᴋɪᴛѕ"
SIZE: 27

FILLER-SLOTS: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26]

FILLER:
  MATERIAL: GRAY_STAINED_GLASS_PANE
  TITLE: " "

STATUS:
  AVAILABLE: "&#00FC00Available"
  COOLDOWN: "&#FC0000Ready in %time%"
  ONE-TIME-USED: "&#FC0000Already claimed"
  NO-PERMISSION: "&#FC0000No access"
```

## `economy/kits/gui/preview.yml`

```yaml
TITLE: "&8ᴘʀᴇᴠɪᴇᴡ"
SIZE: 54

BACK:
  SLOT: 45
  MATERIAL: RED_STAINED_GLASS_PANE
  TITLE: "&#FC0000&lBACK"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fReturn to the"
    - "&fkit menu"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"

REVERT:
  SLOT: 52
  MATERIAL: CHEST_MINECART
  TITLE: "&#FCE300&lREVERT"
  LORE:
    - "&7Action"
    - ""
    - "&#FCE300Information"
    - "&fPut the items back"
    - "&fthe way the kit was built"
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Revert"

SAVE:
  SLOT: 53
  MATERIAL: LIME_STAINED_GLASS_PANE
  TITLE: "&#00FC00&lSAVE"
  LORE:
    - "&7Action"
    - ""
    - "&#00FC00Information"
    - "&fClaim this kit into"
    - "&fyour own arrangement"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Save"
```

## `economy/kits/kits/starter.yml`

```yaml

SLOT: 13

MATERIAL: LIGHT_BLUE_CANDLE

TITLE: "&#00A4FC&lSTARTER"

LORE:
  - "&7Starter Kit Reward"
  - ""
  - "&#00A4FCInformation"
  - "&fEverything a fresh start needs:"
  - "&farmor, tools and a food supply"
  - ""
  - "&#00A4FC▶ &fStatus: %status%"
  - ""
  - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Claim"

permission: "economycore.kit.starter"

permission-required: false

cooldown: 86400

one-time: false

contents:
  hotbar:
    '0':
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:water_bucket
      count: 1
      schema_version: 1
    '1':
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:ender_pearl
      count: 16
      schema_version: 1
    '2':
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:iron_pickaxe
      count: 1
      schema_version: 1
    '3':
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:iron_sword
      count: 1
      schema_version: 1
    '4':
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:iron_axe
      count: 1
      schema_version: 1
    '5':
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:cobblestone
      count: 64
      schema_version: 1
    '6':
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:oak_log
      count: 16
      schema_version: 1
    '8':
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:cooked_beef
      count: 64
      schema_version: 1
  armor:
    helmet:
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:iron_helmet
      count: 1
      schema_version: 1
    chestplate:
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:iron_chestplate
      count: 1
      schema_version: 1
    leggings:
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:iron_leggings
      count: 1
      schema_version: 1
    boots:
      ==: org.bukkit.inventory.ItemStack
      DataVersion: 4671
      id: minecraft:iron_boots
      count: 1
      schema_version: 1
  offhand:
    ==: org.bukkit.inventory.ItemStack
    DataVersion: 4671
    id: minecraft:golden_apple
    count: 16
    schema_version: 1
```

## `economy/kits/messages.yml`

```yaml

messages:
  claimed: "&#00A4FC&lKITS &r&7» &fClaimed the &#00A4FC%kit% &fkit."
  cooldown: "&cYou can claim %kit% &cagain in %time%"
  one-time-used: "&cYou have already claimed %kit%"
  no-permission: "&cYou do not have access to %kit%"
  no-space: "&cClear your inventory before claiming %kit%"
  not-found: "&#00A4FC&lKITS &r&7» &cThat kit does not exist."
  usage: "&#00A4FC&lKITS &r&7» &fUsage: &7/kit claim <kit>"
  layout-saved: "&#00A4FC&lKITS &r&7» &fSaved your layout for &#00A4FC%kit%&f."
  layout-reset: "&#00A4FC&lKITS &r&7» &fReset your layout for &#00A4FC%kit%&f."

manager:
  usage: "&#00A4FC&lKITS &r&7» &fUsage: &7/kitmanager <create|delete|edit> <kit> &for &7give|reset <player> <kit>"
  usage-reset: "&#00A4FC&lKITS &r&7» &fUsage: &7/kitmanager reset <player> <kit>"
  reset: "&#00A4FC&lKITS &r&7» &fReset the &#00A4FC%kit% &fcooldown of &#00A4FC%player%&f."
  not-on-cooldown: "&#00A4FC&lKITS &r&7» &c&#00A4FC%player% &chas no cooldown on &#00A4FC%kit%&c."
  given: "&#00A4FC&lKITS &r&7» &fGave &#00A4FC%kit% &fto &#00A4FC%player%&f."
  received: "&#00A4FC&lKITS &r&7» &fYou received the &#00A4FC%kit% &fkit."

  player-not-found: "&#00A4FC&lKITS &r&7» &cThat player is not online."
  player-unknown: "&#00A4FC&lKITS &r&7» &cNo player by that name has been on this server."
  created: "&#00A4FC&lKITS &r&7» &fCreated kit &#00A4FC%kit% &ffrom your inventory."
  exists: "&#00A4FC&lKITS &r&7» &cA kit named &#00A4FC%kit% &calready exists."
  deleted: "&#00A4FC&lKITS &r&7» &fDeleted kit &#00A4FC%kit%&f."
  not-found: "&#00A4FC&lKITS &r&7» &cThat kit does not exist."
  editor-open: "&#00A4FC&lKITS &r&7» &fEditing &#00A4FC%kit%&f. Arrange the items and click save."
  editor-saved: "&#00A4FC&lKITS &r&7» &fSaved the layout for &#00A4FC%kit%&f."
  invalid-name: "&#00A4FC&lKITS &r&7» &cUse only letters, numbers, - and _ in a kit name."
```

## `economy/kits/sounds.yml`

```yaml

sounds:
  open: "minecraft:block.ender_chest.open|0.7|1.2"
  claim: "minecraft:entity.player.levelup|0.7|1.5"
  error: "minecraft:entity.villager.no|0.7|1.0"
```

