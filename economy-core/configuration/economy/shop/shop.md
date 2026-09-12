# `economy/shop/shop.yml`

Location: `plugins/EconomyCore/economy/shop/shop.yml`

```yaml
CATEGORIES:
  MENU-TITLE: "&8ѕʜᴏᴘ"
  MENU-SIZE: 27
  BLOCKS:
    MATERIAL: GRASS_BLOCK
    DISPLAY-NAME: "&#00FC11&lBLOCKS"
    SLOT: 11
    LORE:
      - "&7Navigation"
      - ""
      - "&#00FC11Information"
      - "&fClick to View"
      - "&fThe Block Shop"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to View"
    OPEN-MENU: "BLOCKS-MENU"
  REDSTONE:
    MATERIAL: REDSTONE
    DISPLAY-NAME: "&#A70808&lREDSTONE"
    SLOT: 12
    LORE:
      - "&7Navigation"
      - ""
      - "&#A70808Information"
      - "&fClick to View"
      - "&fThe Redstone Shop"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to View"
    OPEN-MENU: "REDSTONE-MENU"
  GEAR:
    MATERIAL: DIAMOND_SWORD
    DISPLAY-NAME: "&#1EB8E9&lGEAR"
    SLOT: 13
    LORE:
      - "&7Navigation"
      - ""
      - "&#1EB8E9Information"
      - "&fClick to View"
      - "&fThe Gear Shop"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to View"
    OPEN-MENU: "GEAR-MENU"
  BREWING:
    MATERIAL: BLAZE_POWDER
    DISPLAY-NAME: "&#E7B139&lBREWING"
    SLOT: 14
    LORE:
      - "&7Navigation"
      - ""
      - "&#E7B139Information"
      - "&fClick to View"
      - "&fThe Brewing Shop"
      - ""
      - "&#E7B139▶ &#E7B139&l&nCLICK&r &#E7B139to View"
    OPEN-MENU: "BREWING-MENU"
  SHARD:
    MATERIAL: AMETHYST_SHARD
    DISPLAY-NAME: "&#A303F9&lSHARD SHOP"
    SLOT: 15
    LORE:
      - "&7Navigation"
      - ""
      - "&#A303F9Information"
      - "&fClick to View"
      - "&fThe Shard Shop"
      - ""
      - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to View"
    OPEN-MENU: "SHARD-MENU"

BLOCKS-MENU:
  CURRENCY: MONEY
  TITLE: "&8ʙʟᴏᴄᴋѕ"
  BACK-BUTTON-SLOT: 45
  SIZE: 54

  STONE-ITEM:
    CURRENCY: MONEY
    MATERIAL: "STONE"
    DISPLAY-NAME: "&fStone"
    SLOT: 11
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  SAND-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SAND"
    DISPLAY-NAME: "&fSand"
    SLOT: 12
    PRICE-PER-UNIT: 75.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  DEEPSLATE-ITEM:
    CURRENCY: MONEY
    MATERIAL: "DEEPSLATE"
    DISPLAY-NAME: "&fDeepslate"
    SLOT: 13
    PRICE-PER-UNIT: 200.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  BLACKSTONE-ITEM:
    CURRENCY: MONEY
    MATERIAL: "BLACKSTONE"
    DISPLAY-NAME: "&fBlackstone"
    SLOT: 14
    PRICE-PER-UNIT: 750.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  QUARTZ-BLOCK-ITEM:
    CURRENCY: MONEY
    MATERIAL: "QUARTZ_BLOCK"
    DISPLAY-NAME: "&fQuartz Block"
    SLOT: 15
    PRICE-PER-UNIT: 1000.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  SPRUCE-LOG-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPRUCE_LOG"
    DISPLAY-NAME: "&fSpruce Log"
    SLOT: 20
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  GLOWSTONE-ITEM:
    CURRENCY: MONEY
    MATERIAL: "GLOWSTONE"
    DISPLAY-NAME: "&fGlowstone"
    SLOT: 21
    PRICE-PER-UNIT: 75.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  MUD-ITEM:
    CURRENCY: MONEY
    MATERIAL: "MUD"
    DISPLAY-NAME: "&fMud"
    SLOT: 22
    PRICE-PER-UNIT: 75.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  SEA-LANTERN-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SEA_LANTERN"
    DISPLAY-NAME: "&fSea Lantern"
    SLOT: 23
    PRICE-PER-UNIT: 400.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  BLUE-ICE-ITEM:
    CURRENCY: MONEY
    MATERIAL: "BLUE_ICE"
    DISPLAY-NAME: "&fBlue Ice"
    SLOT: 24
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  PRISMARINE-ITEM:
    CURRENCY: MONEY
    MATERIAL: "PRISMARINE"
    DISPLAY-NAME: "&fPrismarine"
    SLOT: 29
    PRICE-PER-UNIT: 75.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  PRISMARINE-BRICKS-ITEM:
    CURRENCY: MONEY
    MATERIAL: "PRISMARINE_BRICKS"
    DISPLAY-NAME: "&fPrismarine Bricks"
    SLOT: 30
    PRICE-PER-UNIT: 100.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  AMETHYST-BLOCK-ITEM:
    CURRENCY: MONEY
    MATERIAL: "AMETHYST_BLOCK"
    DISPLAY-NAME: "&fAmethyst Block"
    SLOT: 31
    PRICE-PER-UNIT: 1000.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  GLASS-ITEM:
    CURRENCY: MONEY
    MATERIAL: "GLASS"
    DISPLAY-NAME: "&fGlass"
    SLOT: 32
    PRICE-PER-UNIT: 100.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  AZALEA-LEAVES-ITEM:
    CURRENCY: MONEY
    MATERIAL: "AZALEA_LEAVES"
    DISPLAY-NAME: "&fAzalea Leaves"
    SLOT: 33
    PRICE-PER-UNIT: 40.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  SCULK-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SCULK"
    DISPLAY-NAME: "&fSculk"
    SLOT: 38
    PRICE-PER-UNIT: 75.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  OBSIDIAN-ITEM:
    CURRENCY: MONEY
    MATERIAL: "OBSIDIAN"
    DISPLAY-NAME: "&fObsidian"
    SLOT: 39
    PRICE-PER-UNIT: 750.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  CRYING-OBSIDIAN-ITEM:
    CURRENCY: MONEY
    MATERIAL: "CRYING_OBSIDIAN"
    DISPLAY-NAME: "&fCrying Obsidian"
    SLOT: 40
    PRICE-PER-UNIT: 400.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  SOUL-SAND-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SOUL_SAND"
    DISPLAY-NAME: "&fSoul Sand"
    SLOT: 41
    PRICE-PER-UNIT: 40.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"
  MAGMA-BLOCK-ITEM:
    CURRENCY: MONEY
    MATERIAL: "MAGMA_BLOCK"
    DISPLAY-NAME: "&fMagma Block"
    SLOT: 42
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Blocks"
      - ""
      - "&#00FC11Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#00FC11▶ &#00FC11&l&nCLICK&r &#00FC11to Buy"

REDSTONE-MENU:
  TITLE: "&8ʀᴇᴅѕᴛᴏɴᴇ"
  BACK-BUTTON-SLOT: 36
  SIZE: 45
  CURRENCY: MONEY

  REDSTONE-ITEM:
    CURRENCY: MONEY
    MATERIAL: "REDSTONE"
    DISPLAY-NAME: "&fRedstone Dust"
    SLOT: 11
    PRICE-PER-UNIT: 30.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  DISPENSER-ITEM:
    CURRENCY: MONEY
    MATERIAL: "DISPENSER"
    DISPLAY-NAME: "&fDispenser"
    SLOT: 12
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  MINECART-ITEM:
    CURRENCY: MONEY
    MATERIAL: "HOPPER_MINECART"
    DISPLAY-NAME: "&fHopper Minecart"
    SLOT: 13
    PRICE-PER-UNIT: 200.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  HONEY-BLOCK-ITEM:
    CURRENCY: MONEY
    MATERIAL: "HONEY_BLOCK"
    DISPLAY-NAME: "&fHoney Block"
    SLOT: 14
    PRICE-PER-UNIT: 120.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  TARGET-ITEM:
    CURRENCY: MONEY
    MATERIAL: "TARGET"
    DISPLAY-NAME: "&fTarget"
    SLOT: 15
    PRICE-PER-UNIT: 50.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  COMPARATOR-ITEM:
    CURRENCY: MONEY
    MATERIAL: "COMPARATOR"
    DISPLAY-NAME: "&fComparator"
    SLOT: 20
    PRICE-PER-UNIT: 70.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  DROPPER-ITEM:
    CURRENCY: MONEY
    MATERIAL: "DROPPER"
    DISPLAY-NAME: "&fDropper"
    SLOT: 21
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  POWERED-RAIL-ITEM:
    CURRENCY: MONEY
    MATERIAL: "POWERED_RAIL"
    DISPLAY-NAME: "&fPowered Rail"
    SLOT: 22
    PRICE-PER-UNIT: 75.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  SLIME-BLOCK-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SLIME_BLOCK"
    DISPLAY-NAME: "&fSlime Block"
    SLOT: 23
    PRICE-PER-UNIT: 60.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  CRAFTER-ITEM:
    CURRENCY: MONEY
    MATERIAL: "CRAFTER"
    DISPLAY-NAME: "&fCrafter"
    SLOT: 24
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  REPEATER-ITEM:
    CURRENCY: MONEY
    MATERIAL: "REPEATER"
    DISPLAY-NAME: "&fRepeater"
    SLOT: 29
    PRICE-PER-UNIT: 60.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  OBSERVER-ITEM:
    CURRENCY: MONEY
    MATERIAL: "OBSERVER"
    DISPLAY-NAME: "&fObserver"
    SLOT: 30
    PRICE-PER-UNIT: 200.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  HOPPER-ITEM:
    CURRENCY: MONEY
    MATERIAL: "HOPPER"
    DISPLAY-NAME: "&fHopper"
    SLOT: 31
    PRICE-PER-UNIT: 100.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  PISTON-ITEM:
    CURRENCY: MONEY
    MATERIAL: "PISTON"
    DISPLAY-NAME: "&fPiston"
    SLOT: 32
    PRICE-PER-UNIT: 50.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"
  NOTE-BLOCK-ITEM:
    CURRENCY: MONEY
    MATERIAL: "NOTE_BLOCK"
    DISPLAY-NAME: "&fNote Block"
    SLOT: 33
    PRICE-PER-UNIT: 300.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Redstone"
      - ""
      - "&#A70808Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#A70808▶ &#A70808&l&nCLICK&r &#A70808to Buy"

GEAR-MENU:
  TITLE: "&8ɢᴇᴀʀ"
  BACK-BUTTON-SLOT: 45
  SIZE: 54
  CURRENCY: MONEY

  GOLDEN-APPLE-ITEM:
    CURRENCY: MONEY
    MATERIAL: "GOLDEN_APPLE"
    DISPLAY-NAME: "&fGolden Apple"
    SLOT: 11
    PRICE-PER-UNIT: 400.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  EXPERIENCE-BOTTLE-ITEM:
    CURRENCY: MONEY
    MATERIAL: "EXPERIENCE_BOTTLE"
    DISPLAY-NAME: "&fXP Bottle"
    SLOT: 12
    PRICE-PER-UNIT: 100.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  SHULKER-BOX-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SHULKER_BOX"
    DISPLAY-NAME: "&fShulker Box"
    SLOT: 13
    PRICE-PER-UNIT: 2000.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  WIND-CHARGE-ITEM:
    CURRENCY: MONEY
    MATERIAL: "WIND_CHARGE"
    DISPLAY-NAME: "&fWind Charge"
    SLOT: 14
    PRICE-PER-UNIT: 120.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  WATER-BUCKET-ITEM:
    CURRENCY: MONEY
    MATERIAL: "WATER_BUCKET"
    DISPLAY-NAME: "&fWater Bucket"
    SLOT: 15
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  GOLDEN-CARROT-ITEM:
    CURRENCY: MONEY
    MATERIAL: "GOLDEN_CARROT"
    DISPLAY-NAME: "&fGolden Carrot"
    SLOT: 20
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  ENDER-PEARL-ITEM:
    CURRENCY: MONEY
    MATERIAL: "ENDER_PEARL"
    DISPLAY-NAME: "&fEnder Pearl"
    SLOT: 21
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  SHULKER-SHELL-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SHULKER_SHELL"
    DISPLAY-NAME: "&fShulker Shell"
    SLOT: 22
    PRICE-PER-UNIT: 1000.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  COBWEB-ITEM:
    CURRENCY: MONEY
    MATERIAL: "COBWEB"
    DISPLAY-NAME: "&fCobweb"
    SLOT: 23
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  LAVA-BUCKET-ITEM:
    CURRENCY: MONEY
    MATERIAL: "LAVA_BUCKET"
    DISPLAY-NAME: "&fLava Bucket"
    SLOT: 24
    PRICE-PER-UNIT: 300.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  TOTEM-ITEM:
    CURRENCY: MONEY
    MATERIAL: "TOTEM_OF_UNDYING"
    DISPLAY-NAME: "&fTotem of Undying"
    SLOT: 29
    PRICE-PER-UNIT: 10000.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  ENDER-CHEST-ITEM:
    CURRENCY: MONEY
    MATERIAL: "ENDER_CHEST"
    DISPLAY-NAME: "&fEnder Chest"
    SLOT: 30
    PRICE-PER-UNIT: 4000.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  FIRE-ROCKET-ITEM:
    CURRENCY: MONEY
    MATERIAL: "FIREWORK_ROCKET"
    DISPLAY-NAME: "&fFirework Rocket"
    SLOT: 31
    PRICE-PER-UNIT: 150.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  SPECTRAL-ARROW-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPECTRAL_ARROW"
    DISPLAY-NAME: "&fSpectral Arrow"
    SLOT: 32
    PRICE-PER-UNIT: 75.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  STEAK-ITEM:
    CURRENCY: MONEY
    MATERIAL: "COOKED_BEEF"
    DISPLAY-NAME: "&fSteak"
    SLOT: 33
    PRICE-PER-UNIT: 30.0
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  DIAMOND-HELMET-ITEM:
    CURRENCY: MONEY
    MATERIAL: "DIAMOND_HELMET"
    DISPLAY-NAME: "&fDiamond Helmet"
    SLOT: 38
    PRICE-PER-UNIT: 10000.0
    COMMAND: ""
    GIVE-ITEM: true
    ENCHANTMENTS:
      - "PROTECTION:3"
      - "UNBREAKING:2"
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  DIAMOND-CHESTPLATE-ITEM:
    CURRENCY: MONEY
    MATERIAL: "DIAMOND_CHESTPLATE"
    DISPLAY-NAME: "&fDiamond Chestplate"
    SLOT: 39
    PRICE-PER-UNIT: 10000.0
    COMMAND: ""
    GIVE-ITEM: true
    ENCHANTMENTS:
      - "PROTECTION:3"
      - "UNBREAKING:2"
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  DIAMOND-LEGGINGS-ITEM:
    CURRENCY: MONEY
    MATERIAL: "DIAMOND_LEGGINGS"
    DISPLAY-NAME: "&fDiamond Leggings"
    SLOT: 40
    PRICE-PER-UNIT: 10000.0
    COMMAND: ""
    GIVE-ITEM: true
    ENCHANTMENTS:
      - "PROTECTION:3"
      - "UNBREAKING:2"
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  DIAMOND-BOOTS-ITEM:
    CURRENCY: MONEY
    MATERIAL: "DIAMOND_BOOTS"
    DISPLAY-NAME: "&fDiamond Boots"
    SLOT: 41
    PRICE-PER-UNIT: 10000.0
    COMMAND: ""
    GIVE-ITEM: true
    ENCHANTMENTS:
      - "PROTECTION:3"
      - "UNBREAKING:2"
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"
  DIAMOND-SWORD-ITEM:
    CURRENCY: MONEY
    MATERIAL: "DIAMOND_SWORD"
    DISPLAY-NAME: "&fDiamond Sword"
    SLOT: 42
    PRICE-PER-UNIT: 10000.0
    COMMAND: ""
    GIVE-ITEM: true
    ENCHANTMENTS:
      - "SHARPNESS:4"
      - "SWEEPING_EDGE:1"
      - "UNBREAKING:2"
    LORE:
      - "&7Gear"
      - ""
      - "&#1EB8E9Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#1EB8E9▶ &#1EB8E9&l&nCLICK&r &#1EB8E9to Buy"

BREWING-MENU:
  TITLE: "&8ʙʀᴇᴡɪɴɢ"
  BACK-BUTTON-SLOT: 27
  SIZE: 36
  CURRENCY: MONEY

  STRENGTH-POTION-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPLASH_POTION"
    DISPLAY-NAME: "&fSplash Potion of Strength II"
    SLOT: 11
    PRICE-PER-UNIT: 2000.0
    POTION-TYPE: "STRONG_STRENGTH"
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Brewing"
      - ""
      - "&#E7B139Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#E7B139▶ &#E7B139&l&nCLICK&r &#E7B139to Buy"
  REGENERATION-POTION-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPLASH_POTION"
    DISPLAY-NAME: "&fSplash Potion of Regeneration"
    SLOT: 12
    PRICE-PER-UNIT: 2000.0
    POTION-TYPE: "LONG_REGENERATION"
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Brewing"
      - ""
      - "&#E7B139Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#E7B139▶ &#E7B139&l&nCLICK&r &#E7B139to Buy"
  FIRE-RESISTANCE-POTION-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPLASH_POTION"
    DISPLAY-NAME: "&fSplash Potion of Fire Resistance"
    SLOT: 13
    PRICE-PER-UNIT: 3000.0
    POTION-TYPE: "LONG_FIRE_RESISTANCE"
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Brewing"
      - ""
      - "&#E7B139Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#E7B139▶ &#E7B139&l&nCLICK&r &#E7B139to Buy"
  WATER-BREATHING-POTION-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPLASH_POTION"
    DISPLAY-NAME: "&fSplash Potion of Water Breathing"
    SLOT: 14
    PRICE-PER-UNIT: 7500.0
    POTION-TYPE: "LONG_WATER_BREATHING"
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Brewing"
      - ""
      - "&#E7B139Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#E7B139▶ &#E7B139&l&nCLICK&r &#E7B139to Buy"
  HEALING-POTION-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPLASH_POTION"
    DISPLAY-NAME: "&fSplash Potion of Healing II"
    SLOT: 15
    PRICE-PER-UNIT: 1000.0
    POTION-TYPE: "STRONG_HEALING"
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Brewing"
      - ""
      - "&#E7B139Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#E7B139▶ &#E7B139&l&nCLICK&r &#E7B139to Buy"
  INVISIBILITY-POTION-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPLASH_POTION"
    DISPLAY-NAME: "&fSplash Potion of Invisibility"
    SLOT: 20
    PRICE-PER-UNIT: 10000.0
    POTION-TYPE: "LONG_INVISIBILITY"
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Brewing"
      - ""
      - "&#E7B139Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#E7B139▶ &#E7B139&l&nCLICK&r &#E7B139to Buy"
  SWIFTNESS-POTION-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPLASH_POTION"
    DISPLAY-NAME: "&fSplash Potion of Swiftness"
    SLOT: 21
    PRICE-PER-UNIT: 2000.0
    POTION-TYPE: "LONG_SWIFTNESS"
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Brewing"
      - ""
      - "&#E7B139Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#E7B139▶ &#E7B139&l&nCLICK&r &#E7B139to Buy"
  SWIFTNESS2-POTION-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPLASH_POTION"
    DISPLAY-NAME: "&fSplash Potion of Swiftness II"
    SLOT: 22
    PRICE-PER-UNIT: 2000.0
    POTION-TYPE: "STRONG_SWIFTNESS"
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Brewing"
      - ""
      - "&#E7B139Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#E7B139▶ &#E7B139&l&nCLICK&r &#E7B139to Buy"
  LEAPING-POTION-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPLASH_POTION"
    DISPLAY-NAME: "&fSplash Potion of Leaping II"
    SLOT: 23
    PRICE-PER-UNIT: 8000.0
    POTION-TYPE: "STRONG_LEAPING"
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Brewing"
      - ""
      - "&#E7B139Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#E7B139▶ &#E7B139&l&nCLICK&r &#E7B139to Buy"
  TURTLE-MASTER-POTION-ITEM:
    CURRENCY: MONEY
    MATERIAL: "SPLASH_POTION"
    DISPLAY-NAME: "&fSplash Potion of Turtle Master"
    SLOT: 24
    PRICE-PER-UNIT: 120000.0
    POTION-TYPE: "TURTLE_MASTER"
    COMMAND: ""
    GIVE-ITEM: true
    LORE:
      - "&7Brewing"
      - ""
      - "&#E7B139Information"
      - "&fBuy price: &#00FC00%price%"
      - ""
      - "&#E7B139▶ &#E7B139&l&nCLICK&r &#E7B139to Buy"

SHARD-MENU:
  TITLE: "&8ѕʜᴀʀᴅ ѕʜᴏᴘ"
  BACK-BUTTON-SLOT: 27
  SIZE: 36
  CURRENCY: SHARD

  BASIC-KEY-ITEM:
    CURRENCY: SHARD
    MATERIAL: "LIME_CANDLE"
    DISPLAY-NAME: "&#00FC00&lBASIC KEY"
    SLOT: 11
    PRICE-PER-UNIT: 300.0
    COMMAND: "keymanager give %username% basic %amount%"
    GIVE-ITEM: false
    LORE:
      - "&7Shard Shop"
      - ""
      - "&#00FC00Information"
      - "&fBuy price: &#A303F9%price%"
      - ""
      - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Buy"
  GOD-KEY-ITEM:
    CURRENCY: SHARD
    MATERIAL: "YELLOW_CANDLE"
    DISPLAY-NAME: "&#FCE300&lGOD KEY"
    SLOT: 12
    PRICE-PER-UNIT: 700.0
    COMMAND: "keymanager give %username% god %amount%"
    GIVE-ITEM: false
    LORE:
      - "&7Shard Shop"
      - ""
      - "&#FCE300Information"
      - "&fBuy price: &#A303F9%price%"
      - ""
      - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Buy"
  SPAWNER-KEY-ITEM:
    CURRENCY: SHARD
    MATERIAL: "MAGENTA_CANDLE"
    DISPLAY-NAME: "&#A303F9&lSPAWNER KEY"
    SLOT: 13
    PRICE-PER-UNIT: 1500.0
    COMMAND: "keymanager give %username% spawner %amount%"
    GIVE-ITEM: false
    LORE:
      - "&7Shard Shop"
      - ""
      - "&#A303F9Information"
      - "&fBuy price: &#A303F9%price%"
      - ""
      - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to Buy"
  PRIME-KEY-ITEM:
    CURRENCY: SHARD
    MATERIAL: "RED_CANDLE"
    DISPLAY-NAME: "&#FC0000&lPRIME KEY"
    SLOT: 14
    PRICE-PER-UNIT: 2500.0
    COMMAND: "keymanager give %username% prime %amount%"
    GIVE-ITEM: false
    LORE:
      - "&7Shard Shop"
      - ""
      - "&#FC0000Information"
      - "&fBuy price: &#A303F9%price%"
      - ""
      - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Buy"
  MYTHIC-KEY-ITEM:
    CURRENCY: SHARD
    MATERIAL: "LIGHT_BLUE_CANDLE"
    DISPLAY-NAME: "&#00A4FC&lMYTHIC KEY"
    SLOT: 15
    PRICE-PER-UNIT: 3000.0
    COMMAND: "keymanager give %username% mythic %amount%"
    GIVE-ITEM: false
    LORE:
      - "&7Shard Shop"
      - ""
      - "&#00A4FCInformation"
      - "&fBuy price: &#A303F9%price%"
      - ""
      - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Buy"
  COW-SPAWNER-ITEM:
    CURRENCY: SHARD
    MATERIAL: "SPAWNER"
    DISPLAY-NAME: "&#A303F9&lCOW SPAWNER"
    SLOT: 20
    PRICE-PER-UNIT: 350.0
    COMMAND: "vspawner give %username% cow %amount%"
    GIVE-ITEM: false
    LORE:
      - "&7Shard Shop"
      - ""
      - "&#A303F9Information"
      - "&fBuy price: &#A303F9%price%"
      - ""
      - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to Buy"
  SKELETON-SPAWNER-ITEM:
    CURRENCY: SHARD
    MATERIAL: "SPAWNER"
    DISPLAY-NAME: "&#A303F9&lSKELETON SPAWNER"
    SLOT: 21
    PRICE-PER-UNIT: 500.0
    COMMAND: "vspawner give %username% skeleton %amount%"
    GIVE-ITEM: false
    LORE:
      - "&7Shard Shop"
      - ""
      - "&#A303F9Information"
      - "&fBuy price: &#A303F9%price%"
      - ""
      - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to Buy"
  CREEPER-SPAWNER-ITEM:
    CURRENCY: SHARD
    MATERIAL: "SPAWNER"
    DISPLAY-NAME: "&#A303F9&lCREEPER SPAWNER"
    SLOT: 22
    PRICE-PER-UNIT: 625.0
    COMMAND: "vspawner give %username% creeper %amount%"
    GIVE-ITEM: false
    LORE:
      - "&7Shard Shop"
      - ""
      - "&#A303F9Information"
      - "&fBuy price: &#A303F9%price%"
      - ""
      - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to Buy"
  BLAZE-SPAWNER-ITEM:
    CURRENCY: SHARD
    MATERIAL: "SPAWNER"
    DISPLAY-NAME: "&#A303F9&lBLAZE SPAWNER"
    SLOT: 23
    PRICE-PER-UNIT: 1000.0
    COMMAND: "vspawner give %username% blaze %amount%"
    GIVE-ITEM: false
    LORE:
      - "&7Shard Shop"
      - ""
      - "&#A303F9Information"
      - "&fBuy price: &#A303F9%price%"
      - ""
      - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to Buy"
  GOLEM-SPAWNER-ITEM:
    CURRENCY: SHARD
    MATERIAL: "SPAWNER"
    DISPLAY-NAME: "&#A303F9&lIRON GOLEM SPAWNER"
    SLOT: 24
    PRICE-PER-UNIT: 1500.0
    COMMAND: "vspawner give %username% iron_golem %amount%"
    GIVE-ITEM: false
    LORE:
      - "&7Shard Shop"
      - ""
      - "&#A303F9Information"
      - "&fBuy price: &#A303F9%price%"
      - ""
      - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to Buy"
```
