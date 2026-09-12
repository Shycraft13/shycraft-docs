# Placeholders (`config/placeholder.yml`)

Reference of every PlaceholderAPI placeholder provided by economy-core. This file is **info only** and is not read by the plugin.

Requires [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/). Every placeholder starts with `%economy_...%`.

Location: `plugins/EconomyCore/config/placeholder.yml`

## Player

| Placeholder | Description |
| --- | --- |
| `%economy_name%` | Player name |
| `%economy_ping%` | Player ping in ms |
| `%economy_money%` | Balance, formatted (e.g. `12.3k`) |
| `%economy_shards%` | Shard balance |
| `%economy_kills%` | Kills |
| `%economy_deaths%` | Deaths |
| `%economy_playtime%` | Playtime (e.g. `3d 4h 12m`) |
| `%economy_keyall%` | Remaining keyall uses |
| `%economy_team%` | Team name, or `None` |

## RTP zone

| Placeholder | Description |
| --- | --- |
| `%economy_rtpzone_countdown%` | Global countdown until the next teleport, formatted (e.g. `1m 5s`). Works anywhere, so it can drive a title or a hologram. |

## Leaderboards

Syntax:

```
%economy_lb_<type>_<pos>_<field>%     value at a rank
%economy_lb_<type>_position%          the viewing player's own rank
```

- `<type>` — `balance` | `kills` | `deaths` | `playtime` | `shards`
- `<pos>` — rank number, `1` = top
- `<field>` — `name` | `value`

Returns `N/A` if the rank is empty or the player is unranked.

**Examples:**

| Placeholder | Description |
| --- | --- |
| `%economy_lb_balance_1_name%` | Name of #1 richest |
| `%economy_lb_balance_1_value%` | Balance of #1 richest |
| `%economy_lb_kills_3_name%` | Name of #3 killer |
| `%economy_lb_balance_position%` | Your own balance rank |
