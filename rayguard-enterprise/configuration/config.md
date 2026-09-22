# `config.yml`

Location: `plugins/RayGuard-Enterprise/config.yml`

Cross-module settings, license activation, debug flags. Each feature has its own file next to this one.

```yaml
license:
  key: "LIC-XXXXXXXX-XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"

developer-mode: false

async-raytrace-threads: 8

third-person-camera: false
third-person-cam-distance: 4.5
third-person-cam-offset-y: 1.5

debug: false
debug-antixray: false
debug-antifreecam: false
debug-entityculling: false
debug-tileculling: false
debug-chunkprotect: false
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `license.key` | placeholder | Your RayGuard Enterprise license key. Without a valid key the plugin refuses to start. See [Installation](../installation.md) for how to obtain and activate a key. |
| `developer-mode` | `false` | Unlocks the `/rayguard fake` command tree for baking your own fake-world pack. Leave off on a live server. The shipped pack is already tuned, and baking generates a 1024 x 1024 block area which is not for a production server during play hours. |
| `async-raytrace-threads` | `8` | Number of background threads used for line-of-sight work. `8` comfortably covers around 100 concurrent players. Raise if you regularly have many more; lower on very small servers. |
| `third-person-camera` | `false` | Also reveal ores visible from the F5 (third-person) camera position. Without this, ores can pop in when the player switches to third person. Doubles the anti-x-ray ray count. |
| `third-person-cam-distance` | `4.5` | Distance in blocks from the player to the third-person camera. Only used when `third-person-camera: true`. Matches vanilla's F5 offset. |
| `third-person-cam-offset-y` | `1.5` | Vertical offset in blocks for the third-person camera. Only used when `third-person-camera: true`. |
| `debug` | `false` | Master debug switch. Turning this on enables all five feature-specific debug flags below. |
| `debug-antixray` | `false` | Log every ore hide / reveal decision and its line-of-sight result. |
| `debug-antifreecam` | `false` | Log section reveal bursts, cube open / close events and teleport-triggered snapshots. |
| `debug-entityculling` | `false` | Log every entity hide / reveal with the reason. Adds a per-player heartbeat every 5 seconds. |
| `debug-tileculling` | `false` | Log every block-entity hide / reveal (chests, spawners, anvils). |
| `debug-chunkprotect` | `false` | Log decoy scatter and revert decisions. Only meaningful when `chunkprotect.yml` `enabled: true`. |

Keep every debug flag off on a live server. They log per player and per state change, which is noisy fast. `/rayguard reload` picks up debug changes without a restart.
