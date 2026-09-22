# How-to Guides

Quick recipes for common tasks. Each links to the relevant config page for the full option reference.

## Add or remove a world from protection

Every module has its own world list. If your overworld folder is named `smp` instead of `world`, edit each of the following:

- `antifreecam.yml` → `protected-worlds:`
- `entityculling.yml` → `worlds:`
- `tileculling.yml` → `worlds:`
- `chunkprotect.yml` → `worlds:` (only if you have ChunkProtect enabled)
- Rename `anti-xray/world.yml` to `anti-xray/smp.yml` (the file name must match the world folder)

Then `/rayguard reload`.

To skip protection in your spawn or lobby world, remove the world name from those lists. Removing a world from `entityculling.yml` in particular saves noticeable CPU if you have lots of players standing around warp NPCs.

## Turn the fake world off

Set `enabled: false` in [`fakeworld.yml`](configuration/fakeworld.md). Hidden sections will fall back to the plain `fill-block` from `antifreecam.yml` (default: deepslate). Anti-freecam still runs.

## Turn anti-freecam off

Set `enabled: false` in [`antifreecam.yml`](configuration/antifreecam.md). The fake world follows this switch and stops loading. Anti-x-ray, tile culling, entity culling and ChunkProtect all keep running independently.

## Tune anti-x-ray for a specific world

Anti-x-ray is configured per world. Edit `anti-xray/<worldname>.yml`:

- `hidden-blocks:` add or remove ore types.
- `replacementBlocks:` add per-Y-level replacement tiers. The tier with the largest Y-key `≤` the ore's Y applies. See [`anti-xray/world.yml`](configuration/anti-xray/world.md) for the syntax.
- `reveal-distance:` the max distance in blocks at which the plugin reveals an ore the player can see. Lower saves CPU, higher reveals ores through longer sight lines.

Shared tuning (FOV, corner rays, hysteresis) lives once in [`anti-xray/config.yml`](configuration/anti-xray/config.md) and applies to every world.

## Cull the enderman-only preset

Some servers only care about hiding endermen (for end-farm privacy). In `entityculling.yml`, replace the `entity-types:` list with just:

```yaml
entity-types:
  - ENDERMAN
```

Everything else stays visible.

## Hide chests only, leave the rest of the block entities alone

In `tileculling.yml`, trim `tile-entity-blocks:` to the block types you want hidden. To leave chests, leave `CHEST`, `TRAPPED_CHEST`, `BARREL`, `SHULKER_BOX` — remove everything else.

## Prove the plugin is working

Give a staff account the `rayguardenterprise.bypass` permission and a normal account no permission. Mine down to Y=20 in a fresh chunk with both. The staff account sees the real ores; the normal account sees the ore location filled with stone / deepslate until they break the surrounding wall.

For anti-freecam, install a freecam client mod as the normal account and try to fly around underground. You will see baked fake terrain (or a solid `fill-block` cube if the fake world is off), never the real caves.

## Debug a specific feature

Enable the matching debug flag in [`config.yml`](configuration/config.md) (`debug-antixray`, `debug-antifreecam`, `debug-entityculling`, `debug-tileculling`, `debug-chunkprotect`) then `/rayguard reload`. Log lines are prefixed so you can `grep` for the feature you care about. Keep debug off on a live server — the logs are per-player and per state change and get noisy fast.

## Free a machine binding after moving hosts

Your license is bound to the machine it first checked in on. After a host or hardware change the plugin will refuse to start with a binding-limit error.

- Self-service: run `/ipreset` on the [Shycraft Discord](https://discord.gg/MSzB5AxqRp). This frees every machine binding on your key.
- Restart the server. It will re-bind to the new machine on startup.

## Recover a lost license key

Run `/mylicense` on the [Shycraft Discord](https://discord.gg/MSzB5AxqRp). Every key issued to your Discord account is listed with the full copyable key.

## Set up a second server on the same license

By default a license is bound to one machine. If you need more slots, open a **License Support** ticket on the Shycraft Discord and describe your setup. Your slot count can be raised.
