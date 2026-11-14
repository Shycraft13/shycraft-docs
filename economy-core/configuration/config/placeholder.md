# `config/placeholder.yml`

Location: `plugins/EconomyCore/config/placeholder.yml`

A reference list only. The plugin never reads this file, so editing it changes nothing. It exists
so the available placeholders are at hand on the server itself, and it is regenerated with the
plugin's own list.

For the documented list with examples see [Placeholders](../../placeholders.md).

```yaml
# ============================================================================
#  EconomyCore - Placeholders (INFO ONLY, not read by the plugin)
#  Requires PlaceholderAPI. Every placeholder starts with %economy_...%.
# ============================================================================

#  %economy_name%          Player name
#  %economy_ping%          Player ping in ms
#  %economy_money%         Balance, formatted (e.g. 12.3k)
#  %economy_shards%        Shard balance
#  %economy_kills%         Kills
#  %economy_deaths%        Deaths
#  %economy_playtime%      Playtime (e.g. 3d 4h 12m)
#  %economy_keyall%        Remaining keyall uses
#  %economy_team%          Team name, or "None"

# ----------------------------------------------------------------------------
#  RTP Zone (mass-teleport countdown)
# ----------------------------------------------------------------------------
#  %economy_rtpzone_countdown%          Global countdown until the next teleport,
#                                       formatted (e.g. 1m 5s). Works anywhere,
#                                       so it can drive a title or a hologram.

# ----------------------------------------------------------------------------
#  Leaderboards
#    %economy_lb_<type>_<pos>_<field>%   value at a rank
#    %economy_lb_<type>_position%        the viewing player's own rank
#
#    <type>   money | kills | deaths | playtime | shards
#    <pos>    rank number, 1 = top
#    <field>  name | value
#    Returns "N/A" if empty / unranked.
# ----------------------------------------------------------------------------
#  %economy_lb_money_1_name%     Name of #1 richest
#  %economy_lb_money_1_value%    Balance of #1 richest
#  %economy_lb_kills_3_name%     Name of #3 killer
#  %economy_lb_money_position%   Your own balance rank
```
