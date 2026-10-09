# `economy/warp/config.yml`

Location: `plugins/EconomyCore/economy/warp/config.yml`

Settings for `/warp`. `teleport-delay` is the warm-up in seconds before the
teleport fires; `0` teleports instantly. Warps themselves are created in game
with `/warpmanager create <name>` and removed with `/warpmanager delete <name>`.

```yaml
warp:
  teleport-delay: 5
```
