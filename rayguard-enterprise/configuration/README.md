# Configuration

RayGuard Enterprise ships one main config plus one file per feature module.

```
plugins/RayGuard-Enterprise/
├── config.yml            main config (license, debug, threads)
├── antifreecam.yml       chunk-section hiding below max-hidden-y
├── fakeworld.yml         baked terrain for hidden sections
├── entityculling.yml     LOS-based entity hiding
├── tileculling.yml       LOS-based block-entity hiding (chests, spawners, ...)
├── chunkprotect.yml      decoy replacement for buried real terrain (off by default)
├── transparency.yml      shared see-through block list for every module
├── anti-xray/
│   ├── config.yml        shared anti-xray tuning (FOV, corner rays, hysteresis)
│   ├── world.yml         per-world anti-xray (overworld)
│   ├── world_nether.yml  per-world anti-xray (nether)
│   └── world_the_end.yml per-world anti-xray (end)
└── packs/
    └── default.rgpack    shipped fake-world pack, replaced on every upgrade
```

## Pages

- Main
  - [config.yml](config.md) license, debug flags, third-person camera, raytrace threads
- Anti-freecam & fake world
  - [antifreecam.yml](antifreecam.md)
  - [fakeworld.yml](fakeworld.md)
- Anti-x-ray
  - [anti-xray/config.yml](anti-xray/config.md) shared tuning
  - [anti-xray/world.yml](anti-xray/world.md) overworld
  - [anti-xray/world_nether.yml](anti-xray/world_nether.md) nether
  - [anti-xray/world_the_end.yml](anti-xray/world_the_end.md) end
- Culling
  - [entityculling.yml](entityculling.md)
  - [tileculling.yml](tileculling.md)
- Extras
  - [chunkprotect.yml](chunkprotect.md)
  - [transparency.yml](transparency.md)

## Reload semantics

`/rayguard reload` re-reads every YAML in this folder and applies the new values without a restart. Two exceptions:

- **License** is only checked at startup. Changing `license.key` requires a full server restart.
- **`packs/default.rgpack`** is loaded at startup and after `/rayguard fake load`. Editing the pack file on disk without one of those actions has no effect.

## Auto-updating configs

On every startup, each shipped config is rebuilt from the template inside the JAR. The rebuild copies your existing values into the fresh template, so:

- Comments and key ordering always match the current version.
- Values you set are preserved.
- New options that a version added appear in place, with their explanatory comment above them.
- Keys the current template does not know about (e.g. options that were removed) are kept in the file.

You never lose values across upgrades.
