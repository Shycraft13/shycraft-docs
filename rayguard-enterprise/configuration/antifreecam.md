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

fill-block: deepslate

protected-worlds:
  - world

force-chunk-refresh: true
force-chunk-refresh-delay-ticks: 3
force-chunk-refresh-debounce-ms: 750
force-chunk-refresh-unload-first: true
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
| `fill-block` | `deepslate` | Block used to fill hidden sections on the client when the fake world is off or does not cover this Y. Any solid block name works. |
| `protected-worlds` | `[world]` | Worlds where anti-freecam is active. Folder names, case-sensitive. Worlds not on this list are shipped unchanged. |
| `force-chunk-refresh` | `true` | Workaround for a Minecraft 1.21.11 client bug where large reveal bursts leave transparent-face glitches in caves. After each burst on a chunk the plugin resends the chunk a few ticks later so the client rebuilds the mesh cleanly. Cost: about one extra chunk resend per burst per chunk. |
| `force-chunk-refresh-delay-ticks` | `3` | Delay in ticks between the reveal burst and the follow-up chunk resend. |
| `force-chunk-refresh-debounce-ms` | `750` | Per-chunk debounce for the follow-up resend. Prevents a chain of reveals from producing a chain of resends. |
| `force-chunk-refresh-unload-first` | `true` | Tell the client to unload the chunk before the resend. The stronger workaround for the 1.21.11 bug: costs a brief flicker (chunk goes empty for around 20-50 ms) but is the only reliable fix in bad cases. Set to `false` to fall back to a plain resend. |
