# `antifreecam.yml`

Location: `plugins/RayGuard-Enterprise/antifreecam.yml`

Hides entire chunk sections below a configurable Y level on the client. Sections are revealed when the player has line-of-sight to them.

```yaml
enabled: true

max-hidden-y: 30

light-strip-y: 321

cube-height: 16

reveal-distance: 128.0

reveal-range: 5.0

scan-max-y: 65

scan-interval-ticks: 8

max-reveals-per-scan: 15

entity-hiding: true

hide-section-effects: true

surface-fill:
  enabled: true
  thickness: 3
  edge-skirt: 8
  close-holes: 2
  soft-above-sea: 30
  fill-block: stone
  end-fill-block: end_stone

fill-block: deepslate

protected-worlds:
  - world
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `enabled` | `true` | Master switch. Off means no section is ever hidden, no light is stripped and no entity is culled below `max-hidden-y` in any world. The fake world follows this switch and does not load when it is off. |
| `max-hidden-y` | `30` | Sections at or below this Y are hidden until the player has line-of-sight. When the fake world is on, this must stay at or below `pack.bake-max-y` in `fakeworld.yml`; otherwise the boundary between fake terrain and the plain `fill-block` becomes visible. The plugin warns on startup if this is too high. |
| `light-strip-y` | `321` | Strip block-light data from hidden sections up to this Y. `321` strips everywhere; lower to skip stripping near the surface. Stripping light defeats light-based x-ray cheats. |
| `cube-height` | `16` | Height per hidden cube. Must be a multiple of 16. Keep at 16 for vanilla behaviour. |
| `reveal-distance` | `128.0` | Max distance in blocks at which a cube is considered for a line-of-sight reveal check. |
| `reveal-range` | `5.0` | Cubes within this radius of the player are revealed unconditionally, no line-of-sight check performed. |
| `scan-max-y` | `65` | Y up to which the reveal scanner runs. Above this Y the scanner stops and every previously revealed cube is hidden again. This is not `max-hidden-y`: hidden cubes still only reach up to `max-hidden-y`; this controls from how high above the player the scanner sweeps for them. Cannot be set below `max-hidden-y`. |
| `scan-interval-ticks` | `8` | Scan interval in ticks (20 ticks = 1 second). Lower reveals faster and costs more CPU. |
| `max-reveals-per-scan` | `15` | Max sections revealed per player per scan tick. Bounds the network burst when a player teleports into a mined cave. |
| `entity-hiding` | `true` | Also hide entities inside hidden cubes. Prevents mobs from appearing to float through the fill. |
| `hide-section-effects` | `true` | Drop particles, sounds, world events, block actions and break animations whose origin sits inside a hidden section. Your own section is always revealed, so this never mutes anything you do yourself. |
| `surface-fill.enabled` | `true` | Also hide everything under the ground surface above `max-hidden-y`. Every block more than `thickness` layers below the local surface stays filled until the player has line of sight to it, so a freecam sees solid ground under the whole map. Caves, ravines and mines open up the same way as below `max-hidden-y`. With this on, the scan runs at every height and `scan-max-y` no longer stops it. Trade-off: rooms under a roof and cave mouths farther away than `reveal-distance` show the fill block until the player gets line of sight. |
| `surface-fill.thickness` | `3` | Real block layers kept under the surface. |
| `surface-fill.edge-skirt` | `8` | At a chunk border whose neighbour chunk is not known yet, the filled floor is pulled this many blocks below the column's own ground. |
| `surface-fill.close-holes` | `2` | Shafts and holes up to twice this many blocks wide are treated as solid ground, so a 1x1 shaft or a small pit is filled like the terrain around it and opens up by line of sight like a cave. `0` turns it off. |
| `surface-fill.soft-above-sea` | `30` | From this many blocks above sea level, a thin build with air under it (sky base, bridge, map art, house on stilts) does not count as ground and nothing under it is filled. Below that line everything stays filled. |
| `surface-fill.fill-block` | `stone` | Block for filled cells the fake world does not cover (fake world off, or above its baked range). |
| `surface-fill.end-fill-block` | `end_stone` | Block for filled cells in End worlds. The End has no fake world and no `max-hidden-y` zone: only the solid core of each island is filled, so thin islands and the void stay as they are. |
| `fill-block` | `deepslate` | Block used to fill hidden sections on the client when the fake world is off or does not cover this Y. Any solid block name works. |
| `protected-worlds` | `[world]` | Worlds where anti-freecam is active. Folder names, case-sensitive. Worlds not on this list are shipped unchanged. End worlds can be listed too; they use surface fill only. |
