# How-to Guides

Quick walkthroughs for the most common admin tasks. Every action here is a `*manager` command; see the [Commands](commands.md) page for the full syntax.

## Create a kit

Kits are stored under `plugins/EconomyCore/economy/kits/kits/`. You can hand-write the YAML if you want, but the in-game workflow is much easier because it captures your exact inventory layout, slot by slot.

1. Give yourself a clean inventory containing exactly the items and slots you want in the kit.
2. Run `/kitmanager create <name>` — the kit is created from your current inventory, exact slots preserved.
3. Edit the kit's cooldown, permission and display in `economy/kits/kits/<name>.yml`.
4. Test with `/kit claim <name>`. Give the kit to yourself again bypassing the cooldown with `/kitmanager give <you> <name>`.

To edit an existing kit's items later, run `/kitmanager edit <name>` to open the in-game editor.

Full config keys live under [Configuration → economy → kits](configuration/economy/kits/config.md).

## Create an AFK zone

AFK zones are rectangular regions where players earn shards while idling. You need two corners.

1. Run `/afkmanager afkarea wand` — you get the AFK wand.
2. **Left-click** any block for corner 1.
3. **Right-click** any block for corner 2.
4. Run `/afkmanager afkarea create <name>` — the zone is created from those two corners.
5. Reward interval and amount are global, configured in [`economy/afk/config.yml`](configuration/economy/afk/config.md) under `afk.reward`.

Delete with `/afkmanager afkarea delete <name>`.

## Set the AFK teleport target

`/afk` teleports players to a fixed spot. Set that spot with:

1. Stand at the exact position you want players to land at.
2. `/afkmanager setafk`.

## Create an RTP zone

RTP zones are the pool the random-teleport picks from. Same wand-based flow as AFK zones.

1. `/rtpmanager rtpzone wand` — get the wand.
2. Left-click for corner 1, right-click for corner 2.
3. `/rtpmanager rtpzone create <name>`.

Delete with `/rtpmanager rtpzone delete <name>`. The world of each zone is stored with the zone — `/rtp` will match on the current world's zones.

For per-world settings like cooldown and safe-teleport search, see [`economy/rtp/config.yml`](configuration/economy/rtp/config.md).

## Set the server spawn

`/spawn` teleports players to a fixed spot. Configure it with:

1. Stand at the exact position and facing angle you want players to arrive at.
2. `/spawnmanager setspawn`.

## Create a tag

Tags are cosmetic name prefixes. You create them from the game and hand them out to players.

1. Run `/tagsmanager create <tag>` — creates a new empty tag.
2. Edit `plugins/EconomyCore/economy/tags/tags.yml` for the tag's display text and permission requirements (or use `/tagsmanager edit <tag>`).
3. Give a tag to a player with `/tagsmanager give <player> <tag>`. Take it back with `/tagsmanager remove <player> <tag>`.

## Adjust player balance or shards

Fast admin adjustments — no menu needed.

| Task | Command |
| --- | --- |
| Give money | `/moneymanager add <player> <amount>` |
| Take money | `/moneymanager remove <player> <amount>` |
| Set exact balance | `/moneymanager set <player> <amount>` |
| Give shards | `/shardmanager add <player> <amount>` |
| Take shards | `/shardmanager remove <player> <amount>` |
| Set exact shards | `/shardmanager set <player> <amount>` |

## Manage bounties

| Task | Command |
| --- | --- |
| Add to a bounty | `/bountymanager add <player> <amount>` |
| Set an exact bounty | `/bountymanager set <player> <amount>` |
| Subtract from a bounty | `/bountymanager remove <player> <amount>` |
| Wipe a bounty | `/bountymanager clear <player>` |

## Set an item's worth

`/sell` uses per-item prices from `economy/worth/worth.yml`. Set or update them from the game:

1. Hold the item you want to price in your main hand.
2. Run `/worthmanager set hand <price>`.

Or set it by name: `/worthmanager set <item> <price>`.

## Give someone a Mythic Tool

Mythic Tools are temporary premium tools that expire after a set duration.

```
/mythictool give <player> <tool> <time>
```

Example: `/mythictool give Shycraft13 miner 7d` gives the `miner` tool for seven days. Tool definitions live in `economy/mythictools/mythictool.yml`.

## Force a combat tag

Useful when a player logs out mid-fight and you want the tag to stay when they log back in.

```
/combatmanager tag <player> [duration]
/combatmanager untag <player>
/combatmanager untag all
```

Duration accepts formats like `120`, `120s`, `3m`, `1h`. Without a duration the default from `economy/combat/config.yml` is used.

## Force-disband a team

If a team's owner is offline or unresponsive:

```
/teammanager forcedisband <team>
```

You can also view a team's roster and home without joining:

```
/teammanager view <team_or_player>
/teammanager teamhome <team>
```

## Announcements & reminders

Push a one-off message to everyone:

```
/announce <message>
```

Or fire a pre-configured reminder from `economy/announcement/reminder.yml`:

```
/reminder <name>
```

## Reload configs

Every YAML file can be reloaded without a restart:

```
/economy reload
```

Feature flags in `config/config.yml` are re-evaluated. A subsystem turned off during a reload is fully unregistered (commands, listeners, menus).
