# Commands

Every command below is registered dynamically and can be turned off in its feature's config. Every command shows the default alias set from `plugin.yml`; you can rename or add aliases from the per-feature config files.

## Economy

| Command | Aliases | Description |
| --- | --- | --- |
| `/money [player]` | — | Show a balance. |
| `/pay <player> <amount>` | — | Send money to another player. Optional confirmation menu (per-player toggle in `/settings`). |
| `/shards [player]` | — | Show a shard balance. |

## Chat & Messaging

| Command | Aliases | Description |
| --- | --- | --- |
| `/msg <player> <message>` | `/pm` | Send a private message. |
| `/reply <message>` | `/r` | Reply to the last player who messaged you. |
| `/ignore <player>` | — | Toggle ignoring a player's chat and private messages. |
| `/unignore <player>` | — | Stop ignoring a player. |

## Homes

| Command | Description |
| --- | --- |
| `/home [name]` | Teleport to a home. Without a name opens the home menu. |
| `/homes` | Open the home menu. |
| `/sethome <name>` | Create or overwrite a home at your current location. |
| `/delhome <name>` | Delete a home. |

Home limits are permission-based: give players `economy.homes.<n>` to grant up to `n` homes. Highest matching node wins. Default without any node is 2 homes.

## Teleportation (TPA)

| Command | Aliases | Description |
| --- | --- | --- |
| `/tpa <player>` | — | Request to teleport to a player. |
| `/tpahere <player>` | — | Request that a player teleports to you. |
| `/tpaccept` | — | Accept the last incoming request. |
| `/tpadeny` | `/tpdeny`, `/tpacancel` | Deny incoming request or cancel your outgoing one. |
| `/tpauto` | — | Toggle auto-accepting incoming teleport requests. |

## Random Teleport

| Command | Description |
| --- | --- |
| `/rtp [world]` | Random-teleport within the configured zones for the given world. Accepts the world name or its display alias from `config.yml`. |
| `/rtpqueue` | Random-teleport into a 1v1 queue with another player. |

## Spawn & AFK

| Command | Description |
| --- | --- |
| `/spawn` | Teleport to spawn. |
| `/afk` | Teleport to the AFK area, if configured. |

## Sell / Shop / Worth

| Command | Aliases | Description |
| --- | --- | --- |
| `/sell` | — | Open the sell GUI to sell items in your inventory. |
| `/sellhistory [player]` | — | View your (or another player's) sell history. |
| `/sellmulti` | `/sellmultiplier` | View your active sell multipliers. |
| `/shop` | — | Open the configured shop menu. |
| `/worth [item\|hand]` | — | Browse item prices, look up a specific item, or `/worth hand` to check what you're holding. |

## Bounties

| Command | Aliases | Description |
| --- | --- | --- |
| `/bounty` | `/bounties` | Open the bounty menu. |
| `/bounty add <player> <amount>` | — | Place or add to a bounty on a player. |

## Kits

| Command | Description |
| --- | --- |
| `/kit` | Open the kit menu. |
| `/kit claim <name>` | Claim a specific kit. |
| `/kits` | Alias for the kit menu. |

## Tags

| Command | Description |
| --- | --- |
| `/tags` | Open the tag menu to pick a cosmetic tag. |

## Teams

| Command | Description |
| --- | --- |
| `/team create <name>` | Create a team. |
| `/team invite <player>` | Invite a player to your team. |
| `/team accept` | Accept a pending invite. |
| `/team deny` | Deny a pending invite. |
| `/team leave` | Leave your current team. |
| `/team disband` | Disband your team (owner only). |
| `/team kick <player>` | Remove a member (owner or with permission). |
| `/team sethome` | Set the team home. |
| `/team delhome` | Delete the team home. |
| `/team home` | Teleport to the team home. |
| `/team chat` | Toggle team chat mode. |
| `/teamhome` | Shortcut for `/team home`. |

## Stats & Leaderboards

| Command | Aliases | Description |
| --- | --- | --- |
| `/stats [player]` | — | Open the player statistics GUI. |
| `/leaderboard` | `/leaderboards`, `/lb` | Open the leaderboard menu (balance, kills, playtime, shards, bounties). |
| `/baltop` | — | Direct shortcut to the balance leaderboard. |

## Settings

| Command | Description |
| --- | --- |
| `/settings` | Open your personal settings menu (chat toggles, notifications, PM/pay confirmation, and more). |

## Utility Commands

Every utility command opens the vanilla screen for that block from anywhere. `/enderchest` opens your own real ender chest (shared with the physical block). These live in `economy/util/config.yml` and can each be individually turned off, renamed, or given a different permission node.

| Command | Aliases | Opens |
| --- | --- | --- |
| `/enderchest` | `/ec`, `/ender` | Your ender chest |
| `/craft` | `/workbench` | Crafting table |
| `/anvil` | — | Anvil |
| `/grindstone` | `/grind` | Grindstone |
| `/loom` | — | Loom |
| `/cartography` | `/carto` | Cartography table |
| `/smithing` | — | Smithing table |
| `/stonecutter` | — | Stonecutter |
| `/glow [player]` | — | Toggle the entity glow flag on yourself, or on another player (admin). |

## Admin Commands

Every admin command below is gated by `economycore.admin` (default: `op`).

### Player management

| Command | Description |
| --- | --- |
| `/moneymanager <add\|set\|remove> <player> <amount>` | Adjust a player's balance. |
| `/shardmanager <add\|set\|remove> <player> <amount>` | Adjust a player's shard count. |
| `/profilemanager <view\|edit\|wipe> <player> [...]` | Open the admin profile GUI for a player, edit stats, or fully wipe their data. |
| `/homemanager view <player>` | View and manage another player's homes. |
| `/kitmanager give <player> <kit>` | Give a kit to a player, bypassing cooldown checks. |
| `/kitmanager reset <player> <kit>` | Reset a player's kit cooldown. |

### Content management

| Command | Description |
| --- | --- |
| `/kitmanager create <kit>` | Create a new kit. Uses your current inventory as the kit contents (exact slot layout is preserved). |
| `/kitmanager delete <kit>` | Delete a kit. |
| `/kitmanager edit <kit>` | Open the in-game kit editor. |
| `/tagsmanager create <tag>` | Create a new tag from your current view. |
| `/tagsmanager delete <tag>` | Delete a tag. |
| `/tagsmanager edit <tag>` | Edit an existing tag. |
| `/tagsmanager give <player> <tag>` | Give a tag to a player. |
| `/tagsmanager remove <player> <tag>` | Take a tag from a player. |
| `/worthmanager set <item\|hand> <price>` | Set the worth of an item. `hand` uses the item you're holding. |
| `/mythictool give <player> <tool> <time>` | Give a player a timed mythic tool that expires after `<time>`. |

### World & zone management

| Command | Description |
| --- | --- |
| `/spawnmanager setspawn` | Set the server spawn point to your current location. |
| `/afkmanager setafk` | Set the AFK teleport target. |
| `/afkmanager afkarea wand` | Give yourself the AFK-zone wand. Left-click for corner 1, right-click for corner 2. |
| `/afkmanager afkarea create <name>` | Create an AFK zone from the two corners you've selected. |
| `/afkmanager afkarea delete <name>` | Delete an AFK zone. |
| `/rtpmanager rtpzone wand` | Give yourself the RTP-zone wand. Same corner-select flow as the AFK wand. |
| `/rtpmanager rtpzone create <name>` | Create an RTP zone from the two selected corners. |
| `/rtpmanager rtpzone delete <name>` | Delete an RTP zone. |

### Team & combat management

| Command | Description |
| --- | --- |
| `/teammanager view <player_or_team>` | View a team or the team a player is in. |
| `/teammanager forcedisband <team>` | Disband a team without the owner's consent. |
| `/teammanager teamhome <team>` | Teleport to a team's home. |
| `/combatmanager tag <player> [duration]` | Force-combat-tag a player. |
| `/combatmanager untag <player\|all>` | Clear the combat tag from a player, or from everyone. |
| `/bountymanager <add\|set\|remove\|clear> <player> [amount]` | Manage bounties on a player. |

### Broadcasting

| Command | Description |
| --- | --- |
| `/announce <message>` | Broadcast an announcement to all players. |
| `/reminder <name>` | Send a configured reminder from `economy/announcement/reminder.yml` manually. |

### System

| Command | Description |
| --- | --- |
| `/economy reload` | Reload every config file. Feature flags in `config.yml` are re-evaluated: a subsystem turned off during a reload is fully unregistered. |
