# `tileculling.yml`

Location: `plugins/RayGuard-Enterprise/tileculling.yml`

Hides block entities (chests, spawners, signs, anvils, ...) on the client until the player has line-of-sight. Prevents chest and spawner ESP.

```yaml
enabled: true

worlds:
  - world
  - world_nether
  - world_the_end

max-distance: 64.0

corner-rays-enabled: true
corner-rays-interval: 3

min-block-height: -64
max-block-height: 320

replacement-block: AIR

tile-entity-blocks:
  - CHEST
  - TRAPPED_CHEST
  - ENDER_CHEST
  - BARREL
  - SHULKER_BOX
  - HOPPER
  - DROPPER
  - DISPENSER
  - DECORATED_POT
  - FURNACE
  - BLAST_FURNACE
  - SMOKER
  - BREWING_STAND
  - CAMPFIRE
  - SOUL_CAMPFIRE
  - CRAFTER
  - ANVIL
  - ENCHANTING_TABLE
  - BEACON
  - CONDUIT
  - LECTERN
  - CHISELED_BOOKSHELF
  - JUKEBOX
  - BELL
  - BANNER
  - SKULL
  - SPAWNER
  - TRIAL_SPAWNER
  - VAULT
  - BEEHIVE
  - BEE_NEST
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `enabled` | `true` | Master switch. |
| `worlds` | `[world, world_nether, world_the_end]` | Worlds where tile culling runs. Remove worlds you do not want to spend line-of-sight work on. |
| `max-distance` | `64.0` | Max line-of-sight distance in blocks. Block entities beyond this are always hidden. |
| `corner-rays-enabled` | `true` | Every scan runs one cheap center ray. When on, up to 8 corner rays (offset inward from each cube corner) probe for visibility through cracks. Catches "sliver of a chest visible through a diagonal gap" cases. |
| `corner-rays-interval` | `3` | Corner rays only run every Nth scan tick. Higher saves CPU. |
| `min-block-height` / `max-block-height` | `-64` / `320` | Y range. Block entities outside this range are not culled. |
| `replacement-block` | `AIR` | Block used to replace a culled block entity on the client until it reveals. `AIR` makes it fully invisible (cleanest ESP defence). Other options: `STONE`, `DEEPSLATE`, `BARRIER`, or any solid block name. |
| `tile-entity-blocks` | see YAML | Block types hidden until the player has line-of-sight. Only real block entities work here; a block without one (crafting table, smithing table, lodestone) is dropped from the list with a warning. Aliases expand automatically: `SIGN` covers all 48 sign types, `SHULKER_BOX` covers all 17 colours, `ANVIL` covers all three damage states, `BED` covers all 16 colours, `BANNER` covers all 32 (standing + wall), `SKULL` / `HEAD` covers all 14 head variants. |

**BED is intentionally not culled.** A bed is a two-block structure with distinct block-state IDs for foot vs head, but only one half carries the block entity. Culling it leaves the other half in a stale visibility state until a nearby block change forces a rescan, which players notice as "only one half of the bed breaks properly". Beds are not a strong x-ray marker anyway.
