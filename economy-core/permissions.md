# Permissions

Permissions follow the `economycore.<feature>` scheme for player-facing nodes and `economy.<feature>.<action>` for a few older nodes that predate the rename. Most player-facing nodes default to `true` (granted to everyone); admin nodes default to `op`.

## Player-facing nodes

Every basic command has a permission but is on by default. Revoke them if you want to hide a feature from certain players.

| Node | Default | Description |
| --- | --- | --- |
| `economycore.pay` | `true` | Use `/pay`. |
| `economycore.money` | `true` | Use `/money`. |
| `economycore.shards` | `true` | Use `/shards`. |
| `economycore.home` | `true` | Use `/home`, `/homes`, `/sethome`, `/delhome`. |
| `economycore.tpa` | `true` | Use every TPA command. |
| `economycore.rtp` | `true` | Use `/rtp`. |
| `economycore.rtpqueue` | `true` | Use `/rtpqueue`. |
| `economycore.sell` | `true` | Use `/sell`, `/sellhistory`, `/sellmulti`. |
| `economycore.worth` | `true` | Use `/worth`. |
| `economycore.shop` | `true` | Use `/shop`. |
| `economycore.stats` | `true` | Use `/stats`. |
| `economycore.leaderboard` | `true` | Use `/leaderboard`, `/baltop`. |
| `economycore.bounty` | `true` | Place bounties with `/bounty`. |
| `economycore.team` | `true` | Use `/team` commands. |
| `economycore.settings` | `true` | Open `/settings`. |
| `economycore.spawn` | `true` | Use `/spawn`. |
| `economycore.afk` | `true` | Use `/afk`. |
| `economycore.kit` | `true` | Use `/kit`, `/kits`. |
| `economycore.tags` | `true` | Use `/tags`. |
| `economycore.ignore` | `true` | Use `/ignore`, `/unignore`. |

## Utility commands

Every utility command has its own node so you can grant a subset, matching the `permission` field in `economy/util/config.yml`.

| Node | Default | Description |
| --- | --- | --- |
| `economy.util.enderchest` | `true` | `/enderchest` |
| `economy.util.workbench` | `true` | `/craft` |
| `economy.util.anvil` | `true` | `/anvil` |
| `economy.util.grindstone` | `true` | `/grindstone` |
| `economy.util.loom` | `true` | `/loom` |
| `economy.util.cartography` | `true` | `/cartography` |
| `economy.util.smithing` | `true` | `/smithing` |
| `economy.util.stonecutter` | `true` | `/stonecutter` |
| `economy.glow.use` | `true` | `/glow` on self. |
| `economy.glow.others` | `op` | `/glow <player>` on someone else, including offline targets. |

## Home limits

Home count is granted via a numeric permission node. Highest matching node wins.

| Node | Default | Description |
| --- | --- | --- |
| `economy.homes.1` | `false` | Allow up to 1 home. |
| `economy.homes.2` | `true` | Allow up to 2 homes (default for everyone). |
| `economy.homes.3` | `false` | Allow up to 3 homes. |
| `economy.homes.4` | `false` | Allow up to 4 homes. |
| `economy.homes.5` | `false` | Allow up to 5 homes. |
| `economy.homes.6` | `false` | Allow up to 6 homes. |
| `economy.homes.7` | `false` | Allow up to 7 homes. |
| `economy.homes.8` | `false` | Allow up to 8 homes. |
| `economy.homes.9` | `false` | Allow up to 9 homes. |
| `economy.homes.10` | `false` | Allow up to 10 homes. |

## Combat

| Node | Default | Description |
| --- | --- | --- |
| `economy.combat.bypass` | `op` | Never be tagged into combat by dealing or receiving PvP damage. |
| `economy.combat.commandbypass` | `op` | Run any normally-allowed command while combat-tagged. |

## RTP cooldown override

`economy.rtp.cooldown.<seconds>` sets a custom RTP cooldown for the player. If several are granted, the lowest wins.

Examples:

| Node | Description |
| --- | --- |
| `economy.rtp.cooldown.30` | 30-second cooldown. |
| `economy.rtp.cooldown.0` | No cooldown at all. |

## Shards everywhere

`economy.shards.everywhere.amount.<n>` is the SOLE gate for earning shards outside AFK zones. Granting the node both enables earning AND sets the per-interval amount to `n`. Highest granted amount wins. Also requires `shards-everywhere.enabled: true` in `economy/afk/config.yml`.

| Node | Description |
| --- | --- |
| `economy.shards.everywhere.amount.5` | 5 shards per interval anywhere on the server. |

## Admin

| Node | Default | Description |
| --- | --- | --- |
| `economycore.admin` | `op` | Full access to every `*manager` command, `/announce`, `/reminder`, `/mythictool`, and `/economy reload`. |
