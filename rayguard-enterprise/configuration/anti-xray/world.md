# `anti-xray/world.yml`

Location: `plugins/RayGuard-Enterprise/anti-xray/world.yml`

Per-world anti-x-ray configuration for the overworld. **The file name (without `.yml`) must match the world folder.** If your overworld folder is named `smp`, rename this file to `smp.yml`.

Shared tuning (FOV, corner rays, hysteresis) lives once in [`config.yml`](config.md).

```yaml
enabled: true

max-block-height: 128

reveal-distance: 64.0

update-radius: 2

hidden-blocks:
  - COAL_ORE
  - DEEPSLATE_COAL_ORE
  - IRON_ORE
  - DEEPSLATE_IRON_ORE
  - COPPER_ORE
  - DEEPSLATE_COPPER_ORE
  - GOLD_ORE
  - DEEPSLATE_GOLD_ORE
  - REDSTONE_ORE
  - DEEPSLATE_REDSTONE_ORE
  - LAPIS_ORE
  - DEEPSLATE_LAPIS_ORE
  - DIAMOND_ORE
  - DEEPSLATE_DIAMOND_ORE
  - EMERALD_ORE
  - DEEPSLATE_EMERALD_ORE

replacementBlocks:
  0: STONE
  -64: DEEPSLATE
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `enabled` | `true` | Anti-x-ray active for this world. |
| `max-block-height` | `128` | Highest Y at which ores are hidden. Ores above this Y are sent as-is. |
| `reveal-distance` | `64.0` | Max line-of-sight distance in blocks for per-ore reveal checks. |
| `update-radius` | `2` | Radius (blocks) around a broken or exploded block for an immediate re-check. Makes mining feel instant: as soon as you break an ore, its neighbours reveal in the same tick instead of on the next scan interval. |
| `hidden-blocks` | overworld ore list | Ore types hidden on the client until the player has line-of-sight. Removing an ore from this list makes it visible to everyone; adding one makes it eligible for hiding. |
| `replacementBlocks` | `{0: STONE, -64: DEEPSLATE}` | Per-Y-level replacement blocks. For a hidden ore at world Y=y, the tier with the largest Y-key `≤` y applies. Below the lowest configured tier the lowest entry extends downward, so you do not need to enumerate every bedrock layer. **Example:** `STONE` from Y=0 upward, `DEEPSLATE` from Y=-64 down to bedrock. To add a granite-tier band from Y=32-63, insert `32: GRANITE`. |
