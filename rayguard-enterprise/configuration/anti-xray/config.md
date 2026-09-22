# `anti-xray/config.yml`

Location: `plugins/RayGuard-Enterprise/anti-xray/config.yml`

Shared tuning for anti-x-ray. Applies to every per-world anti-x-ray config in the same folder. Per-world ore lists and replacement blocks live in [`world.yml`](world.md), [`world_nether.yml`](world_nether.md), [`world_the_end.yml`](world_the_end.md).

```yaml
fov-enabled: false
fov-reveal-deg: 110.0
fov-hide-deg: 125.0

distance-buffer: 5.0
rehide-debounce: 6

corner-rays-enabled: true
corner-rays-interval: 3

movement-throttle-blocks: 2.0
movement-throttle-degrees: 8.0

max-candidates-per-tick: 200
max-rehides-per-tick: 100
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `fov-enabled` | `false` | Only reveal ores inside a cone in front of the viewer. Saves CPU but causes revealed ores to briefly pop on fast camera rotation. Off ships as the safer default (distance + line-of-sight only, no rotation pop). |
| `fov-reveal-deg` | `110.0` | Half-angle in degrees of the reveal cone. Ores inside this cone may be revealed. Only used when `fov-enabled: true`. |
| `fov-hide-deg` | `125.0` | Half-angle in degrees of the hide cone. Ores outside this cone are re-hidden. Must be greater than or equal to `fov-reveal-deg`. The gap between the two is a hysteresis band that prevents flicker on small rotations near the cone edge. |
| `distance-buffer` | `5.0` | Extra distance in blocks added before re-hiding a revealed ore. Prevents flicker at the reveal-distance edge. |
| `rehide-debounce` | `6` | Number of consecutive scans an ore must fail line-of-sight before being re-hidden. Higher is smoother and cheaper CPU, lower is faster to re-hide. |
| `corner-rays-enabled` | `true` | Every scan starts with a cheap center ray. When corner rays are on and the center is blocked, up to 8 corner rays (offset inward from each cube corner) probe for visibility through cracks. Backface-culled with early exit, typical extra cost is 2-4 rays per blocked ore. Catches around 95% of "ore visible through a tiny gap" cases (vs around 75% with center-only). |
| `corner-rays-interval` | `3` | Corner rays only run every Nth scan tick. Higher saves CPU, slower to reveal through cracks. |
| `movement-throttle-blocks` | `2.0` | Skip re-scanning a stationary player until they have moved at least this many blocks since the last scan. Anti-x-ray still runs on block break / place, so this only affects the periodic sweep. |
| `movement-throttle-degrees` | `8.0` | Or rotated at least this many degrees. |
| `max-candidates-per-tick` | `200` | Hard cap on how many ore candidates a player can process per scan tick. Excess work spills to the next tick. |
| `max-rehides-per-tick` | `100` | Hard cap on how many ore re-hide updates a player can receive per scan tick. |
