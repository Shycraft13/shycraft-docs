# `fakeworld.yml`

Location: `plugins/RayGuard-Enterprise/fakeworld.yml`

Fills anti-freecam's hidden sections with baked terrain from a different world instead of the plain `fill-block`. Caves, ores and strata that simply are not where the cheater thinks. Ships on by default with a pre-baked `default.rgpack`.

```yaml
enabled: true

worlds: []

pack:
  file: "default.rgpack"
  source-world: ""
  source-chunk-x: 0
  source-chunk-z: 0
  bake-min-y: -64
  bake-max-y: 32
  chunks-per-tick: 4

light:
  ambient: 0

placement:
  seed: ""
  rotation: true
  mirror: true

entities:
  enabled: true
  whitelist:
    - "villager"
    - "wandering_trader"
    - "item_frame"
    - "glow_item_frame"
    - "painting"
    - "armor_stand"
  max-per-chunk: 32
  fake-players:
    enabled: true
    chance: 70
    armor: true
    fetch-skins: true
    names:
      - "Frostbyte"
      - "xNoScope_"
      - "Voidcrit"
      - "Sweatlord"
      - "AimAssistNo"
      - "ClutchOrKick"
      - "Rodmaster"
      - "PearlDiff"
      - "TapsOnly"
      - "CritMachine"
      - "Godbridger"
      - "ShieldSpam"
    skins: []
```

## Top-level keys

| Key | Default | Description |
| --- | --- | --- |
| `enabled` | `true` | Master switch. Off falls back to `antifreecam.yml`'s plain `fill-block` for every hidden section. |
| `worlds` | `[]` (empty) | Worlds where hidden sections show fake terrain. Empty means every world that anti-freecam already protects. |

## `pack`

Which pack file to serve, and where the next `/rayguard fake bake` will source from.

| Key | Default | Description |
| --- | --- | --- |
| `pack.file` | `"default.rgpack"` | File name under `plugins/RayGuard-Enterprise/packs/`. The shipped default is unpacked on first start. |
| `pack.source-world` | `""` (empty) | Source world folder for the next bake. Must **not** be a world listed in `antifreecam.yml`'s `protected-worlds`. Usually written by `/rayguard fake source`, not by hand. |
| `pack.source-chunk-x` / `pack.source-chunk-z` | `0` / `0` | Source-area corner in chunk coordinates. The bake covers 64 x 64 chunks from this corner, so `-32 -32` covers blocks `-512..511` on both axes. |
| `pack.bake-min-y` | `-64` | Lowest Y baked into the pack. |
| `pack.bake-max-y` | `32` | Highest Y baked into the pack. Must be at or above `antifreecam.yml`'s `max-hidden-y`; the plugin warns otherwise. |
| `pack.chunks-per-tick` | `4` | Chunk requests issued per tick during a bake. `4` per tick against 4096 chunks is around 51 seconds plus whatever chunk generation costs. Raise on an empty server for a faster bake. |

## `light`

| Key | Default | Description |
| --- | --- | --- |
| `light.ambient` | `0` | Minimum block-light level (0-15) for every fake section. Leave at 0 for realism. Baked sections use the real block light from the source world; sections the bake found no light for get an emitter flood-fill from the pack's own blocks using vanilla's emission rules. A mostly dark pack is correct, not broken. Raise for debugging only. |

## `placement`

The pack's 64 tiles are placed by a hash of the seed and the tile coordinates, then rotated / mirrored into 512 distinct appearances so the underground does not read as a repeating grid at freecam range.

| Key | Default | Description |
| --- | --- | --- |
| `placement.seed` | `""` (empty) | Per-server salt. Change it and the whole fake underground reshuffles. Empty is treated as 0. Fine for testing; on production use a value nobody else can guess. |
| `placement.rotation` | `true` | Rotate tiles in 90-degree increments. Off only to debug placement. |
| `placement.mirror` | `true` | Mirror tiles on the X and Z axes. Off only to debug placement. |

## `entities`

Bake the source world's entities into the pack and replay them to clients as display-only figures. Item frames keep their item, villagers keep their profession, displays keep their transformation.

**Version note:** entity data is captured in the exact wire format of the Minecraft version the bake ran on. After a Minecraft update the pack reports the old protocol and the runtime drops all entities until you rebake. Terrain is unaffected. `/rayguard fake info` shows both numbers.

| Key | Default | Description |
| --- | --- | --- |
| `entities.enabled` | `true` | Include entities in the pack. Off makes the fake world terrain-only. |
| `entities.whitelist` | `[villager, wandering_trader, item_frame, glow_item_frame, painting, armor_stand]` | Entity types that get baked. With or without the `minecraft:` prefix. Players are always excluded. Keep this to what a survival player actually has standing in a base: furniture and villagers look right standing still, a zombie or a dropped item does not. |
| `entities.max-per-chunk` | `32` | Hard cap per source chunk. Stops one decorated room from dominating the pack. |

## `entities.fake-players`

Barrier blocks in the source world become fake players standing in that spot. Display-only figures: no tab entry, no nametag, no collision, no AI, no movement. The barrier itself is removed from the baked terrain (an invisible wall in a cave gives the fake world away faster than a missing figure would).

| Key | Default | Description |
| --- | --- | --- |
| `fake-players.enabled` | `true` | Turn fake players on. |
| `fake-players.chance` | `70` | Percent chance that a given barrier gets a figure. Below 100 some spots stay empty, which is more realistic than every marked spot being occupied on every tile. Decided at bake time and hashed from the block position, so two players see the same figures and a restart does not re-roll them. Changing this value requires a rebake to take effect. `0` disables every figure. `100` populates every barrier. |
| `fake-players.armor` | `true` | Position-stable random netherite armour with mixed trims. Never changes for a given barrier. |
| `fake-players.fetch-skins` | `true` | Resolve every name in `names:` to that account's real Mojang skin. Uses two public endpoints, no auth. Cached in memory for the session. Failures too, so this costs one request per name per start. `/rayguard fake skins` refetches. |
| `fake-players.names` | 12-name gamer list | Names picked per figure position. Max 16 characters. With `fetch-skins: true`, the figure wears the skin belonging to the name. Use names of accounts that do **not** play on your server. A figure that looks exactly like a regular is not a decoy, it is a misunderstanding waiting to happen. The name is never rendered (no tab entry, no nametag). |
| `fake-players.skins` | `[]` (empty) | Fallback signed `textures` property pairs (`value:` + `signature:`) for names Mojang did not resolve and for when `fetch-skins: false`. Empty is fine: the client then shows the default Steve or Alex derived from the fake UUID. |

## Block entities

Every block entity inside the baked Y range is copied with its NBT, with no filter and no cap. This is intentional: a skipped one leaves a blank sign or a spawner showing the client default. Spawners in particular are the clearest case, the block state says "spawner" and nothing about what spins inside it. Block entities share `entities.enabled` and the same protocol gate: rebake after a Minecraft update.
