# Permissions

Permissions follow the `economycore.<feature>.<action>` scheme. Most player-facing nodes default to `true` (granted to everyone); admin nodes default to `op`.

## Economy

| Node | Default | Description |
| --- | --- | --- |
| `economycore.pay` | `true` | Use `/pay`. |
| `economycore.balance` | `true` | Use `/balance`. |
| `economycore.balance.others` | `op` | See other players' balances. |

## Homes

| Node | Default | Description |
| --- | --- | --- |
| `economycore.homes` | `true` | Use `/home`, `/sethome`, `/delhome`. |
| `economycore.homes.limit.<n>` | `-` | Grants a home limit of `n`. Highest matching node wins. Example: `economycore.homes.limit.5`. |

## Teleportation

| Node | Default | Description |
| --- | --- | --- |
| `economycore.tpa` | `true` | Send TPA requests. |
| `economycore.back` | `true` | Use `/back`. |
| `economycore.rtp` | `true` | Use `/rtp`. |

## Teams

| Node | Default | Description |
| --- | --- | --- |
| `economycore.team` | `true` | Use `/team` commands. |

## Bounties

| Node | Default | Description |
| --- | --- | --- |
| `economycore.bounty` | `true` | Place bounties. |

## Kits

| Node | Default | Description |
| --- | --- | --- |
| `economycore.kit` | `true` | Claim kits. |
| `economycore.kit.<name>` | `-` | Grants access to a specific kit. |

## Utility commands

Each utility command has its own node so you can grant a subset.

| Node | Default | Description |
| --- | --- | --- |
| `economycore.util.enderchest` | `true` | `/enderchest` |
| `economycore.util.workbench` | `true` | `/craft` |
| `economycore.util.anvil` | `true` | `/anvil` |
| `economycore.util.grindstone` | `true` | `/grindstone` |
| `economycore.util.loom` | `true` | `/loom` |
| `economycore.util.cartography` | `true` | `/cartography` |
| `economycore.util.smithing` | `true` | `/smithing` |
| `economycore.util.stonecutter` | `true` | `/stonecutter` |
| `economycore.glow.use` | `true` | `/glow` on self. |
| `economycore.glow.others` | `op` | `/glow <player>` on someone else, including offline targets. |

## Admin

| Node | Default | Description |
| --- | --- | --- |
| `economycore.admin` | `op` | Full access to every `*manager` command and `/economycore reload`. |
