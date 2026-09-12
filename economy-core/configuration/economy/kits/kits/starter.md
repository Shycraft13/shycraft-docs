# `economy/kits/kits/starter.yml`

Location: `plugins/EconomyCore/economy/kits/kits/starter.yml`

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
