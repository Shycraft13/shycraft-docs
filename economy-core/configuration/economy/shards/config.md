# `economy/shards/config.yml`

Location: `plugins/EconomyCore/economy/shards/config.yml`

> Servers upgrading from an older build: on first start after the update, the
> plugin renames the existing `economy/afk/` folder to `economy/shards/`
> automatically. Your edits are preserved. No manual copy is required.

```yaml
afk:
  teleport-delay: 5
  reward:
    # enabled: false = players get NO shards while standing in an AFK zone.
    enabled: true
    interval-seconds: 60
    shards-per-interval: 1

# Shards everywhere: earn shards anywhere on the server, not just in AFK zones.
# Disabled by default. Even with enabled: true, a player only earns if they hold
#   economy.shards.everywhere.amount.<N>
# That node is the SOLE gate: it both grants the earning and sets shards-per-interval
# to <N> (opt-in per rank). There is no separate on/off node. If several are granted
# the HIGHEST value wins. This amount also applies inside AFK zones (it beats
# afk.reward.shards-per-interval there too).
shards-everywhere:
  enabled: false
  interval-seconds: 60
  shards-per-interval: 1

# Shards on kill: killing another player awards shards. There is a per-victim
# cooldown so farming the same target does nothing until it expires. Each
# (killer, victim) pair has its own cooldown, so killing player A does not
# delay the reward for killing player B. Suicides never reward, and neither
# does a kill that has no player killer (mob, environment, /kill).
shards-per-kill:
  enabled: true
  amount: 10
  cooldown-seconds: 86400
  # Sent to the killer only when shards are actually awarded. Nothing is sent
  # when the kill is skipped because the victim is still on the killer's
  # cooldown, so cooldown-blocked kills stay silent.
  # Placeholders: %amount% = shards granted, %player% = victim name.
  message: "&#A303F9&lSHARDS &r&7» &fYou earned &#A303F9%amount% shards &ffrom killing &#FCE300%player%&f."
```
