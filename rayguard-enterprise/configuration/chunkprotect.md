# `chunkprotect.yml`

Location: `plugins/RayGuard-Enterprise/chunkprotect.yml`

Replaces buried real-terrain blocks with random decoy blocks on the client. Purely visual, evaluated once per chunk sent to a player.

**Off by default in Enterprise.** ChunkProtect runs a 26-neighbour occlusion test per eligible block across the whole Y range for every chunk sent. Turn it on only after measuring that your server has the CPU headroom.

**Recommendation:** leave off while the fake world is on. The fake world already shows a full, plausible underground in every hidden section, so decoys mainly cover the sections outside that zone, and you pay the full per-block occlusion cost for it. Turn ChunkProtect on when the fake world is off, or when you deliberately want the sections revealed inside the hidden zone decoyed too and have the CPU headroom.

```yaml
enabled: false

worlds:
  - world

reveal-radius: 6

min-y: -64
max-y: 64

replacement-blocks:
  - oak_stairs
  - cobblestone_stairs
  - deepslate_brick_stairs
  - oak_slab
  - cobblestone_slab
  - deepslate_brick_slab
  - cobblestone_wall
  - stone_brick_wall
  - deepslate_brick_wall
  - oak_fence
  - spruce_fence
  - nether_brick_fence
  - iron_bars
  - iron_chain
  - oak_button
  - stone_button
  - polished_blackstone_button
  - end_stone
  - cobbled_deepslate
  - cobblestone
  - amethyst_cluster
  - kelp_plant
  - bamboo
  - vine
  - candle
  - white_candle
  - black_candle

replaceable-blocks:
  - stone
  - granite
  - diorite
  - andesite
  - tuff
  - deepslate
  - dripstone_block
  - calcite
  - dirt
  - coarse_dirt
  - rooted_dirt
  - mud
  - clay
  - gravel
  - sand
  - red_sand
  - sandstone
  - red_sandstone
  - netherrack
  - basalt
  - blackstone
  - end_stone
  - coal_ore
  - deepslate_coal_ore
  - iron_ore
  - deepslate_iron_ore
  - copper_ore
  - deepslate_copper_ore
  - gold_ore
  - deepslate_gold_ore
  - redstone_ore
  - deepslate_redstone_ore
  - lapis_ore
  - deepslate_lapis_ore
  - diamond_ore
  - deepslate_diamond_ore
  - emerald_ore
  - deepslate_emerald_ore
  - nether_gold_ore
  - nether_quartz_ore
  - ancient_debris
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `enabled` | `false` | Master switch. |
| `worlds` | `[world]` | Worlds where ChunkProtect runs. Outside this list the chunk is sent unchanged. |
| `reveal-radius` | `6` | Real terrain within this radius of the player is shown (decoys flipped back). Higher gives smoother digging and more network traffic. `0` disables the reveal (decoys stay decoys until the block itself breaks). |
| `min-y` | `-64` | Lowest Y eligible for decoy replacement. |
| `max-y` | `64` | Highest Y eligible for decoy replacement. |
| `replacement-blocks` | curated list | Decoy block pool. Each chunk Y-layer picks one random block from this list (stable across restarts). The shipped list is curated for maximum x-ray confusion without tanking client FPS: connected-texture blocks (stairs, slabs, walls, fences, bars, buttons), full blocks and low-cost decoration. Blocks deliberately kept out include lanterns, lit candles, end / lightning rods (continuous particle emitters), amethyst buds (pulsing animation), chorus / dripleaf (random-tick spam) and cobweb (client-side collision recompute). |
| `replaceable-blocks` | see YAML | Real-terrain blocks eligible for decoy replacement. Anything not in this list is sent to the client unchanged. Ores are in the list on purpose: buried ores get ChunkProtect's varied decoy cover so they blend with the surrounding buried terrain. Exposed ores (an ore with a transparent neighbour) are left alone by ChunkProtect by design; those still get anti-x-ray's replacement block from `anti-xray/<world>.yml`. |

## Composition with the fake world

The two never touch the same block, but the split is per section, not per Y level: a section that anti-freecam replaced (fill block or fake terrain) is skipped entirely by ChunkProtect; every other section in the Y range below gets decoys. That includes sections a player has already revealed inside the hidden zone, which would otherwise ship raw terrain. So `min-y` down to the world floor is the intended setup, both with and without the fake world.
