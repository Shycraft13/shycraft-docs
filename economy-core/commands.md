# Commands

Every command below is registered dynamically and can be turned off in its feature's config. Aliases in the tables are the defaults; almost every command lets you rename or add aliases from config.

## Economy

| Command | Description |
| --- | --- |
| `/balance [player]` | Show a balance. Alias: `/bal`, `/money`. |
| `/pay <player> <amount>` | Send money to another player. Optional confirm menu (per-player toggle). |
| `/baltop` | Balance leaderboard GUI. |

## Shards

| Command | Description |
| --- | --- |
| `/shards [player]` | Show a shard balance. |
| `/shardstop` | Shard leaderboard GUI. |

## Homes

| Command | Description |
| --- | --- |
| `/sethome <name>` | Create or overwrite a home. |
| `/home [name]` | Teleport to a home. Without a name opens the home GUI. |
| `/delhome <name>` | Delete a home. |
| `/homes` | List / manage all your homes in a GUI. |

## Teleportation

| Command | Description |
| --- | --- |
| `/tpa <player>` | Request to teleport to a player. |
| `/tpahere <player>` | Request that a player teleports to you. |
| `/tpaccept` | Accept the last incoming request. |
| `/tpdeny` | Deny the last incoming request. |
| `/tpacancel` | Cancel your outgoing request. |
| `/back` | Return to your previous location. |
| `/rtp [world]` | Random-teleport within the configured zones. Accepts the world name or its display alias. |

## Teams

| Command | Description |
| --- | --- |
| `/team create <name>` | Create a team. |
| `/team invite <player>` | Invite a player. |
| `/team join <name>` | Accept a pending invite. |
| `/team leave` | Leave your current team. |
| `/team kick <player>` | Remove a member. |
| `/team home` | Teleport to the team home. |
| `/team sethome` | Set the team home. |
| `/team pvp` | Toggle intra-team PvP. |
| `/team info [team]` | Show info about a team. |

## Bounties

| Command | Description |
| --- | --- |
| `/bounty <player> <amount>` | Place or add to a bounty on a player. |
| `/bounty list` | Open the bounty leaderboard GUI. |
| `/bounty info <player>` | Show a specific bounty. |

## Kits

| Command | Description |
| --- | --- |
| `/kit [name]` | Claim a kit. Without a name opens the kit menu. |
| `/kits` | Alias for the kit menu. |

## Chat

| Command | Description |
| --- | --- |
| `/ignore <player>` | Block a player's chat and pings. |
| `/unignore <player>` | Remove a player from your ignore list. |
| `/ignorelist` | Show your current ignore list. |

## Utility commands

Every utility command below opens the vanilla screen for that block from anywhere. `/enderchest` opens your own real ender chest (shared with the physical block).

| Command | Alias | Opens |
| --- | --- | --- |
| `/enderchest` | `/ec`, `/ender` | Your ender chest |
| `/craft` | `/workbench` | Crafting table |
| `/anvil` |  | Anvil |
| `/grindstone` | `/grind` | Grindstone |
| `/loom` |  | Loom |
| `/cartography` | `/carto` | Cartography table |
| `/smithing` |  | Smithing table |
| `/stonecutter` |  | Stonecutter |
| `/glow [player]` |  | Toggle the entity glow flag on yourself, or on another player (admin). |

While any utility screen is open, further utility commands are rejected. This prevents client mods that let players run commands from inside an inventory from chaining opens.

## Admin

Every admin command is gated by the `economycore.admin` permission and is meant for staff use.

| Command | Description |
| --- | --- |
| `/moneymanager <add\|set\|remove> <player> <amount>` | Adjust a player's balance. |
| `/shardmanager <add\|set\|remove> <player> <amount>` | Adjust a player's shard count. |
| `/kitmanager <create\|delete\|edit\|give\|reset>` | Manage kits and reset a player's cooldowns. |
| `/teammanager <forcedisband\|view\|teamhome>` | Admin team management. |
| `/bountymanager <add\|set\|remove\|clear>` | Manage bounties. |
| `/combatmanager <tag\|untag> <player\|all>` | Force combat-tag or clear it. |
| `/worthmanager set <item\|hand> <price>` | Set the worth of an item for the sell system. |
| `/profilemanager <player>` | Open the admin profile GUI for a player. |
| `/homemanager <player>` | Manage another player's homes. |
| `/economycore reload` | Reload every config file. |
