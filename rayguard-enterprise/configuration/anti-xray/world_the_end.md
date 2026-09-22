# `anti-xray/world_the_end.yml`

Location: `plugins/RayGuard-Enterprise/anti-xray/world_the_end.yml`

Per-world anti-x-ray configuration for the end. **The file name (without `.yml`) must match the world folder.** If your end folder is named `smp_the_end`, rename this file to `smp_the_end.yml`.

The end has no ores worth hiding in vanilla, so `hidden-blocks:` ships empty. Add entries only if your worldgen adds custom ores.

Shared tuning (FOV, corner rays, hysteresis) lives once in [`config.yml`](config.md).

```yaml
enabled: true

max-block-height: 128

reveal-distance: 48.0

update-radius: 2

hidden-blocks:

replacementBlocks:
  0: END_STONE
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `enabled` | `true` | Anti-x-ray active for the end. Harmless with an empty `hidden-blocks:` list; enable and add ores if your worldgen has any. |
| `max-block-height` | `128` | Highest Y at which ores are hidden. |
| `reveal-distance` | `48.0` | Max line-of-sight distance for per-ore reveal checks. |
| `update-radius` | `2` | Radius around a broken block for immediate re-check. |
| `hidden-blocks` | empty | Ores hidden until line-of-sight. Vanilla end has none; fill in for custom worldgen. |
| `replacementBlocks` | `{0: END_STONE}` | One tier (`END_STONE`) covers everything. |
