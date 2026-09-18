# Placeholders

Every placeholder starts with `%economy_...%`. Requires [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) on the server. Use them in scoreboard, tab-list, hologram, chat-format or any other plugin that supports PlaceholderAPI.

## Player placeholders

| Placeholder | Returns | Example |
| --- | --- | --- |
| `%economy_player%` | Player name | `Shycraft13` |
| `%economy_ping%` | Player ping in milliseconds | `42` |
| `%economy_money%` | Balance, formatted with a suffix | `12.3k`, `4.2m` |
| `%economy_shards%` | Shard balance (raw integer) | `1250` |
| `%economy_kills%` | Player kill count | `87` |
| `%economy_deaths%` | Player death count | `21` |
| `%economy_playtime%` | Playtime in `Xd Xh Xm` form | `3d 4h 12m` |
| `%economy_keyall%` | Remaining `/keyall` uses for this player | `2` |
| `%economy_team%` | Team name, or `None` if the player has no team | `Vanguard` |

## RTP zone placeholders

For the mass-teleport RTP zone system, useful in a title or hologram to show players when the next batch teleport happens.

| Placeholder | Returns | Example |
| --- | --- | --- |
| `%economy_rtpzone_countdown%` | Global countdown until the next teleport, formatted | `1m 5s` |

## Leaderboard placeholders

Syntax:

```
%economy_lb_<type>_<pos>_<field>%     value at a specific rank
%economy_lb_<type>_position%          the viewing player's own rank
```

- `<type>` — one of `money`, `kills`, `deaths`, `playtime`, `shards`
- `<pos>` — the rank number, `1` being the top spot
- `<field>` — either `name` (the player's name) or `value` (the metric value)

If the rank is empty or the player is unranked, the placeholder returns `N/A`.

### Examples

| Placeholder | Returns |
| --- | --- |
| `%economy_lb_money_1_name%` | Name of the richest player |
| `%economy_lb_money_1_value%` | Balance of the richest player |
| `%economy_lb_money_2_name%` | Name of the 2nd-richest player |
| `%economy_lb_kills_3_name%` | Name of the #3 killer |
| `%economy_lb_kills_3_value%` | Kill count of the #3 killer |
| `%economy_lb_playtime_1_name%` | Player with the most playtime |
| `%economy_lb_playtime_1_value%` | That player's playtime, formatted |
| `%economy_lb_shards_1_value%` | Top shard balance |
| `%economy_lb_money_position%` | Your own balance rank |
| `%economy_lb_kills_position%` | Your own kill rank |

### Common uses

- **Scoreboard sidebar** — show top 3 richest / top 3 killers on the right side of every player's screen.
- **Tab list header/footer** — show the viewer's own balance and rank.
- **Hologram** — put a "Top 10 Richest" hologram at spawn using DecentHolograms or similar.
- **Chat format** — prefix chat with a player's team and balance.
