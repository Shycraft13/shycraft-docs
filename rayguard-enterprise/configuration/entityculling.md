# `entityculling.yml`

Location: `plugins/RayGuard-Enterprise/entityculling.yml`

Hides entities on the client until the player has line-of-sight to them. Prevents player-tracer and mob-ESP.

```yaml
enabled: true

worlds:
  - world
  - world_nether
  - world_the_end

max-distance: 64.0

fov-enabled: false
fov-half-angle: 70.0

max-checks-per-scan: 50

corner-rays-enabled: true
corner-rays-interval: 3

min-block-height: -64
max-block-height: 320

bounding-box-expansion: 0.3

player-only-sneaking: true

entity-types:
  - PLAYER
  - ENDERMAN
  - BLAZE
  - WITCH
  - MINECART
  - ITEM_FRAME
  - GLOW_ITEM_FRAME
  - PAINTING
  - ARMOR_STAND
  - VILLAGER
  - WANDERING_TRADER
  - ZOMBIE_VILLAGER
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `enabled` | `true` | Master switch. |
| `worlds` | `[world, world_nether, world_the_end]` | Worlds where entity culling runs. Remove your spawn or lobby world here: culling players near a warp NPC burns CPU for no benefit. |
| `max-distance` | `64.0` | Max line-of-sight distance in blocks. Entities beyond this are always hidden. |
| `fov-enabled` | `false` | Also hide entities outside a cone in front of the viewer. Saves CPU but causes entities to briefly disappear when you turn fast. Off ships as the safer default (distance + line-of-sight only, no rotation pop). |
| `fov-half-angle` | `70.0` | Half-angle in degrees for the field-of-view cone. Only used when `fov-enabled: true`. |
| `max-checks-per-scan` | `50` | Max entity hide / reveal events per player per scan tick. Bounds the network burst when teleporting into a packed area. |
| `corner-rays-enabled` | `true` | Every scan runs one cheap center ray. When corner rays are on, two extra rays fire (top and bottom center of the hitbox) to catch "only head / feet visible through a gap" cases. |
| `corner-rays-interval` | `3` | Corner rays only run every Nth scan tick. Higher saves CPU, slower to reveal through cracks. |
| `min-block-height` / `max-block-height` | `-64` / `320` | Y range. Entities outside this range are not culled. |
| `bounding-box-expansion` | `0.3` | How much to expand the entity bounding box for the line-of-sight test. Higher is more lenient (less culling), lower is tighter (more culling). |
| `player-only-sneaking` | `true` | Only cull other players while they are sneaking. Non-sneaking players show their nametag through walls anyway, so culling them adds no defence and causes visual glitches. Recommended to keep on. |
| `entity-types` | see YAML | Entity types subject to culling. Anything not listed is always visible. Aliases expand automatically: `MINECART` covers all seven minecart types, `BOAT` covers all wood and chest and raft variants. |
