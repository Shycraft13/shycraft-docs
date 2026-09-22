# `anti-xray/world_nether.yml`

Location: `plugins/RayGuard-Enterprise/anti-xray/world_nether.yml`

Per-world anti-x-ray configuration for the nether. **The file name (without `.yml`) must match the world folder.** If your nether folder is named `smp_nether`, rename this file to `smp_nether.yml`.

Shared tuning (FOV, corner rays, hysteresis) lives once in [`config.yml`](config.md).

```yaml
enabled: true

max-block-height: 128

reveal-distance: 48.0

update-radius: 2

hidden-blocks:
  - NETHER_GOLD_ORE
  - NETHER_QUARTZ_ORE
  - ANCIENT_DEBRIS

replacementBlocks:
  0: NETHERRACK
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `enabled` | `true` | Anti-x-ray active for the nether. |
| `max-block-height` | `128` | Highest Y at which ores are hidden. |
| `reveal-distance` | `48.0` | Max line-of-sight distance for per-ore reveal checks. Lower than the overworld default because the nether has denser terrain and heavier ancient-debris counts near bastions. |
| `update-radius` | `2` | Radius around a broken block for immediate re-check. |
| `hidden-blocks` | `[NETHER_GOLD_ORE, NETHER_QUARTZ_ORE, ANCIENT_DEBRIS]` | Nether ores hidden until line-of-sight. |
| `replacementBlocks` | `{0: NETHERRACK}` | The nether is one tier (`NETHERRACK`) across the whole build range. One entry covers everything. |
