# `economy/warp/messages.yml`

Location: `plugins/EconomyCore/economy/warp/messages.yml`

Chat output of `/warp` and `/warpmanager`. Placeholders: `%warp%` (the warp
name) and `%warps%` (the comma-separated list of every warp).

```yaml
messages:
  usage: "&cUsage: /warp <name>"
  list: "&7Warps: &f%warps%"
  no-warps: "&cNo warps have been set."
  not-found: "&cWarp &f%warp% &cdoes not exist."
  teleporting: "&#00A4FC&lWARP &r&7» &fTeleporting to &f%warp%&f..."
  already-teleporting: "&cYou are already teleporting."

  warpmanager-no-permission: "&cYou don't have permission."
  warpmanager-usage:         "&cUsage: /warpmanager <create|delete> <name>"
  warpmanager-only-players:  "&cOnly players can create warps."
  warp-created:              "&#00A4FC&lWARP &r&7» &fWarp &f%warp% &fcreated."
  warp-deleted:              "&#00A4FC&lWARP &r&7» &fWarp &f%warp% &fdeleted."
```
