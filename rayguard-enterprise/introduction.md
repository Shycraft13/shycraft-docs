# Introduction

**RayGuard Enterprise** is an anti-x-ray and anti-freecam plugin for Paper-based Minecraft servers. It hides ores until a player can actually see them, hides underground until a player has actually mined into it, and can replace that hidden underground with fake terrain instead of the usual solid deepslate wall.

## What's inside

- **Anti-x-ray** ores are replaced with the surrounding stone / deepslate / netherrack on the client until the player has line-of-sight to them. Independent per-world configuration and per-Y-level replacement tiers, so overworld ores turn into deepslate under Y=0 and stone above.
- **Anti-freecam** entire chunk sections below a configurable Y level are hidden until the player has line-of-sight. Freecam, no-fog and cave-viewer clients see one solid cube instead of the terrain, so they cannot preview caves from the surface. Sections reveal as soon as the player mines into them.
- **Fake world** (on by default) instead of showing a uniform solid cube where the terrain is hidden, the client sees baked terrain taken from a different place: plausible caves, ores and strata that simply are not where the cheater thinks. Ships with a pre-baked pack, no baking required to try it.
- **Tile culling** chests, spawners, signs, anvils, beacons and every other block entity in your ore list are hidden until the player has line-of-sight. Prevents chest / spawner ESP.
- **Entity culling** players, endermen, item frames and other configured entity types are hidden until the player has line-of-sight. Prevents player-tracer / mob-ESP.
- **Third-person camera coverage** (optional) also runs the reveal check from the F5 camera position, so ores do not pop in when you switch view.
- **ChunkProtect** (optional) replaces buried real terrain blocks with random decoy blocks on the client. Off by default. Composes with the fake world.
- **Bypass permission** staff with the bypass node see the raw world, useful for testing.

## Design goals

- **Server-side only.** No client mod, no resource pack. The plugin filters what the server sends to the client. Any vanilla client, any launcher, any mod loader on the client-side sees the filtered view.
- **Per-world tuning.** Every module has its own world list. You can hide overworld ores but leave the nether alone, or the reverse.
- **YAML-only customisation.** Every threshold, block list, per-world tier and reveal radius is in a config file. No recompile required.
- **Zero-config first start.** The shipped defaults protect the overworld and the nether with sensible values. Drop the JAR in, paste your license key, restart — the server is protected.

## Version compatibility

- **Minecraft**: 1.21+
- **Server software**: Paper 1.21+ (and Paper forks, Folia supported)
- **Java**: 21
- **Required plugin**: PacketEvents (any recent release)
- **Optional plugin**: LuckPerms (respected for the bypass permission)

## Licensing

RayGuard Enterprise is a paid plugin sold on BuiltByBit. Each license is bound to your Minecraft server on first startup. See [Installation](installation.md) for how to paste your key and what happens when the key is valid, missing, or fails to check in. Keys are managed by the Shycraft Discord bot: run `/mylicense` on the Shycraft Discord to see your keys, `/ipreset` to free the machine binding after a hardware or host change. Both commands are documented on the [Shycraft Discord](https://discord.gg/MSzB5AxqRp).
