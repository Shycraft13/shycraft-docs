# `gamemodes/config.yml`

Location: `plugins/StaffCore/gamemodes/config.yml`

Behaviour of the `/gamemode` feature: cross-server routing and offline
target support. Command availability is gated by `features.gamemodes` in
[`config/config.yml`](../config/config.md); this file only tunes the two
optional paths.

```yaml
gamemodes:
  cross-server: true
  offline-enabled: true
  notify-target: true
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `gamemodes.cross-server` | `true` | Per-feature gate on top of the network-wide `cross-server.enabled` in [`config/config.yml`](../config/config.md). BOTH must be on for a `/gamemode` issued here to reach a target on another backend, or to fan an offline change out to the node that holds the target's `.dat`. When off, `/gamemode` only affects online players on the same backend and offline players whose `.dat` lives here. |
| `gamemodes.offline-enabled` | `true` | Allow gamemode changes on offline players. When true, the sender's backend either writes the target's `.dat` here (if it holds the file) or fans a broadcast so the node that holds it writes. When false, `/gamemode` on an offline player is rejected with an error. |
| `gamemodes.notify-target` | `true` | Send the `gamemode.target-notify` chat message to the target when a staff member changes their gamemode. Turn off for a silent change (only the sender sees feedback). |

## Interaction with `features.gamemodes`

If `features.gamemodes: false` in [`config/config.yml`](../config/config.md),
no gamemode command is registered on this backend at all. The keys in this
file are ignored until the master switch is on.
