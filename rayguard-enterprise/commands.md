# Commands

RayGuard Enterprise registers a single command: `/rayguard`. Everything is a subcommand.

## Admin

| Command | Permission | Description |
| --- | --- | --- |
| `/rayguard reload` | `rayguardenterprise.reload` | Re-read every YAML under `plugins/RayGuard-Enterprise/`. Modules pick up the new values without a restart. The license is not re-checked on reload; a license change requires a full server restart. |

## Fake world (developer mode)

The `/rayguard fake` subtree is only registered when `developer-mode: true` is set in `config.yml` **and** the caller has `rayguardenterprise.fakeworld`. Both are required. The bake commands are for producing a custom fake-world pack; the shipped `default.rgpack` is already tuned for a live server. Baking generates a large area (1024 x 1024 blocks by default) and is not something you want to run on a production node during play hours.

| Command | Description |
| --- | --- |
| `/rayguard fake info` | Print the currently loaded pack: file, entity / block-entity counts, baked vs derived light section counts, protocol version match. |
| `/rayguard fake source <world> <chunkX> <chunkZ>` | Set the source area for the next bake. Writes into `fakeworld.yml`. The source world must **not** be listed as a protected world in `antifreecam.yml`. |
| `/rayguard fake bake` | Bake the source area into a `.rgpack` file. Uses the settings in `fakeworld.yml` (min/max Y, chunks per tick, entity whitelist). Progress is streamed to the console. |
| `/rayguard fake load` | Load the pack named in `fakeworld.yml`'s `pack.file`. Runs automatically at startup; use this after replacing a pack file at runtime. |
| `/rayguard fake skins` | Re-fetch every Mojang skin listed in `fakeworld.yml`'s `fake-players.names`. Useful when a player has changed their skin. |

For the full fake-world model see [`fakeworld.yml`](configuration/fakeworld.md).

## Namespaced form

If you happen to run another plugin that also registers `/rayguard`, use `/rayguard-enterprise:rayguard <subcommand>` to disambiguate. Only relevant on test setups.
