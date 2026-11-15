# `economy/mythictools/mythictool.yml`

Location: `plugins/EconomyCore/economy/mythictools/mythictool.yml`

```yaml
TREECHOPPER:
  PARTICLE:
    NAME: FALLING_DUST
    MATERIAL: PURPLE_CONCRETE_POWDER
    AMOUNT: 10
  BLOCKS-PER-TICK: 3
  DELAY-TICKS: 2
  FORTUNE-SILK-SWITCH: true
  NAME: "&#00A4FC&lMYTHIC TREECHOPPER"
  LORE:
    - "&7Breaks Trees Instantly"
    - "&8Self Destruct: %time%"
  ENCHANTMENTS:
    - EFFICIENCY:5
    - SILK_TOUCH:1
    - UNBREAKING:3
    - MENDING:1

DRILL:
  PARTICLE:
    NAME: FALLING_DUST
    MATERIAL: PURPLE_CONCRETE_POWDER
    AMOUNT: 10
  DISABLED-BLOCKS:
    - GRASS_BLOCK
    - DIRT_PATH
    - DIRT
    - COARSE_DIRT
    - SAND
    - GRAVEL
    - SPAWNER
  FORTUNE-SILK-SWITCH: true
  NAME: "&#00A4FC&lMYTHIC DRILL"
  LORE:
    - "&79 Blocks Per Break"
    - "&8Self Destruct: %time%"
  ENCHANTMENTS:
    - EFFICIENCY:5
    - SILK_TOUCH:1
    - UNBREAKING:3
    - MENDING:1

MULTITOOL:
  PARTICLE:
    NAME: FALLING_DUST
    MATERIAL: PURPLE_CONCRETE_POWDER
    AMOUNT: 10
  FORTUNE-SILK-SWITCH: true
  NAME: "&#00A4FC&lMYTHIC MULTITOOL"
  LORE:
    - "&7Mines Everything Optimally"
    - "&8Self Destruct: %time%"
  ENCHANTMENTS:
    - EFFICIENCY:5
    - FORTUNE:3
    - UNBREAKING:3
    - MENDING:1

SELLAXE:
  PARTICLE:
    NAME: FALLING_DUST
    MATERIAL: PURPLE_CONCRETE_POWDER
    AMOUNT: 10
  NAME: "&#00A4FC&lMYTHIC SELLAXE"
  LORE:
    - "&7Sells Chest & Barrel Contents"
    - "&8Self Destruct: %time%"
  ENCHANTMENTS:
    - EFFICIENCY:5
    - UNBREAKING:3
    - MENDING:1

FIREWORK:
  PARTICLE:
    NAME: FIREWORK
    AMOUNT: 8
  FLIGHT-DURATION: 1
  COOLDOWN-SECONDS: 1
  NAME: "&#00A4FC&lMYTHIC FIREWORK"
  LORE:
    - "&7Never consumed"
    - "&8Self Destruct: %time%"

SHOVEL:
  PARTICLE:
    NAME: FALLING_DUST
    MATERIAL: PURPLE_CONCRETE_POWDER
    AMOUNT: 10
  DISABLED-BLOCKS:
    - DIRT_PATH
    - FARMLAND
  FORTUNE-SILK-SWITCH: true
  NAME: "&#00A4FC&lMYTHIC SHOVEL"
  LORE:
    - "&79 Blocks Per Break"
    - "&8Self Destruct: %time%"
  ENCHANTMENTS:
    - EFFICIENCY:5
    - SILK_TOUCH:1
    - UNBREAKING:3
    - MENDING:1

BUCKET:
  PARTICLE:
    NAME: FALLING_DUST
    MATERIAL: PURPLE_CONCRETE_POWDER
    AMOUNT: 10
  SIZE: 3
  BLOCKS-PER-TICK: 7
  DELAY-TICKS: 1
  CLEAR-WATERLOGGED: true
  NAME: "&#00A4FC&lMYTHIC BUCKET"
  LORE:
    - "&7Clears Water And Lava 3x3x3"
    - "&8Self Destruct: %time%"

HASTEPOTION:
  EFFECT-DURATION: "16h"
  COLOR: "#FCE300"
  NAME: "&#00A4FC&lMYTHIC HASTE POTION"
  LORE:
    - "&7Haste II for &f%duration%"
    - "&7Stays through death and totems"
    - "&8Self Destruct: %time%"

SHARDBOOSTER:
  EFFECT-DURATION: "24h"
  MULTIPLIER: 2.0
  COLOR: "#A303F9"
  NAME: "&#00A4FC&lMYTHIC SHARD BOOSTER"
  LORE:
    - "&7x%multiplier% shards for &f%duration%"
    - "&8Self Destruct: %time%"
```
