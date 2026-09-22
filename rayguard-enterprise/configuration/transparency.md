# `transparency.yml`

Location: `plugins/RayGuard-Enterprise/transparency.yml`

Shared see-through block list used by every module: anti-x-ray (rays pass through, ores behind glass reveal correctly), anti-freecam (cubes visible through glass are not kept hidden), tile and entity culling (chests / mobs behind glass reveal). Air, water, lava and cave-air variants are always transparent and do not need to be listed.

```yaml
blocks:
  - glass
  - tinted_glass
  - white_stained_glass
  - orange_stained_glass
  - magenta_stained_glass
  - light_blue_stained_glass
  - yellow_stained_glass
  - lime_stained_glass
  - pink_stained_glass
  - gray_stained_glass
  - light_gray_stained_glass
  - cyan_stained_glass
  - purple_stained_glass
  - blue_stained_glass
  - brown_stained_glass
  - green_stained_glass
  - red_stained_glass
  - black_stained_glass
  - glass_pane
  - white_stained_glass_pane
  - orange_stained_glass_pane
  - magenta_stained_glass_pane
  - light_blue_stained_glass_pane
  - yellow_stained_glass_pane
  - lime_stained_glass_pane
  - pink_stained_glass_pane
  - gray_stained_glass_pane
  - light_gray_stained_glass_pane
  - cyan_stained_glass_pane
  - purple_stained_glass_pane
  - blue_stained_glass_pane
  - brown_stained_glass_pane
  - green_stained_glass_pane
  - red_stained_glass_pane
  - black_stained_glass_pane

  - oak_leaves
  - spruce_leaves
  - birch_leaves
  - jungle_leaves
  - acacia_leaves
  - dark_oak_leaves
  - mangrove_leaves
  - cherry_leaves
  - azalea_leaves
  - flowering_azalea_leaves
  - pale_oak_leaves
  - vine
  - kelp
  - kelp_plant
  - seagrass
  - tall_seagrass

  - iron_bars
  - ice
  - cobweb
  - ladder
  - scaffolding
  - iron_chain
  - bell
  - sea_lantern
  - barrier
  - light
  - structure_void
  - glow_lichen
  - sculk_vein
  - snow
  - short_grass
  - tall_grass

  - oak_door
  - spruce_door
  - birch_door
  - jungle_door
  - acacia_door
  - dark_oak_door
  - mangrove_door
  - cherry_door
  - iron_door
  - oak_trapdoor
  - spruce_trapdoor
  - birch_trapdoor
  - jungle_trapdoor
  - acacia_trapdoor
  - dark_oak_trapdoor
  - mangrove_trapdoor
  - cherry_trapdoor
  - iron_trapdoor

  - STAIRS
  - SLAB
  - WALL
  - FENCE
  - FENCE_GATE
  - BUTTON
  - PRESSURE_PLATE
  - CARPET
  - SAPLING
  - FLOWER
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `blocks` | see YAML | Blocks the line-of-sight raytrace treats as transparent. Aliases expand to every variant automatically: `STAIRS` covers all 50+ stair types (oak, stone, deepslate, ...), `SLAB` covers all slab types, `WALL` covers cobble / stone / deepslate walls (NOT wall_signs), `FENCE` covers all fence types, `FENCE_GATE` covers all fence gates, `BUTTON` covers all buttons, `PRESSURE_PLATE` covers all pressure plates, `CARPET` covers all carpet colours, `SAPLING` covers all saplings, `FLOWER` covers all flower types. |

## Why partial-cube blocks are in the list

Blocks that do not fill a full voxel (stairs, slabs, buttons, carpet) look see-through in game but occupy a full cube in the block map. Without them in the transparency list, a chest sitting behind a stair or slab would never reveal: the line-of-sight raycast would hit the stair voxel and report "blocked" even though the chest is clearly visible to the player.

## Legacy block names

`chain` was renamed to `iron_chain` in Minecraft 1.21.9. The loader accepts both and falls back to the old name on older servers.
