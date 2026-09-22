# `gamemodes/messages.yml`

Location: `plugins/StaffCore/gamemodes/messages.yml`

Chat strings shown by `/gamemode`, `/gm`, `/gms`, `/gmc`, `/gma`, `/gmsp`.
Legacy `&` colours and `&#RRGGBB` hex are both accepted.

**Placeholders:** `%player%`, `%mode%`, `%server%`, `%staff%`.

```yaml
common:
  no-permission:              "&cYou lack the permission to run this command."
  no-permission-console:      "&cConsole must specify a target player."
  player-not-found:           "&cPlayer not found."
  cross-server-off-global:    "&cCross-server networking is disabled on this backend."
  cross-server-off-feature:   "&cCross-server gamemode is disabled for this feature."

gamemode:
  usage-generic:              "&7Usage: &f/gamemode <survival|creative|adventure|spectator|0-3> [player]"
  unknown-mode:               "&cUnknown gamemode: &f%mode%&c. Use one of: survival, creative, adventure, spectator (or 0-3)."
  self-changed:               "&7Your gamemode is now &f%mode%&7."
  applied-online:             "&7Set &f%player%&7's gamemode to &f%mode%&7."
  applied-online-remote:      "&7Set &f%player%&7's gamemode to &f%mode%&7 on &f%server%&7."
  applied-offline:            "&7Set offline &f%player%&7's gamemode to &f%mode%&7."
  applied-offline-remote:     "&7Offline gamemode change queued for &f%player% &7(&f%mode%&7)."
  route-failed:               "&cGamemode change failed: no route to the target."
  target-notify:              "&7Your gamemode was set to &f%mode%&7 by &f%staff%&7."
```

## Message keys

| Key | Fires when |
| --- | --- |
| `common.no-permission` | Sender lacks the per-mode node (`staffcore.gamemode.survival` etc.) or `staffcore.gamemode.other` when targeting another player. |
| `common.no-permission-console` | `/gm`, `/gms`, `/gmc`, `/gma`, `/gmsp` invoked from console with no target argument. |
| `common.player-not-found` | Target name did not resolve to any known player (not online anywhere, not in the local cache, not returned by Mojang). |
| `common.cross-server-off-global` | Target is on another backend but `cross-server.enabled` is off network-wide. |
| `common.cross-server-off-feature` | Target is on another backend but `gamemodes.cross-server` is off for this feature. |
| `gamemode.usage-generic` | `/gamemode` invoked with no arguments. |
| `gamemode.unknown-mode` | The mode argument to `/gamemode` did not match any of the accepted spellings or numeric ids. |
| `gamemode.self-changed` | Sender changed their own gamemode. |
| `gamemode.applied-online` | Sender changed another online player's gamemode; the target is on this backend. |
| `gamemode.applied-online-remote` | Sender changed another online player's gamemode; the target is on `%server%` and the change was routed there. |
| `gamemode.applied-offline` | Sender changed an offline player's gamemode; the `.dat` write happened on this backend. Requires `staffcore.gamemode.offline`. |
| `gamemode.applied-offline-remote` | Sender changed an offline player's gamemode; the write was fanned out over Redis for whichever node holds the `.dat`. |
| `gamemode.route-failed` | Change could not be routed (no live target, no local `.dat`, and Redis is unavailable or `gamemodes.cross-server` is off). |
| `gamemode.target-notify` | Target receives this when a staff member changes their gamemode. Only sent when `gamemodes.notify-target: true`. |

## Accepted mode names

The mode argument on `/gamemode` accepts multiple spellings, all
case-insensitive:

| Mode | Accepted |
| --- | --- |
| Survival | `survival`, `s`, `0` |
| Creative | `creative`, `c`, `1` |
| Adventure | `adventure`, `a`, `2` |
| Spectator | `spectator`, `sp`, `3` |

The shortcut commands (`/gms`, `/gmc`, `/gma`, `/gmsp`) hard-wire the mode
and take no mode argument.
