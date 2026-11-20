# `economy/combat/config.yml`

Location: `plugins/EconomyCore/economy/combat/config.yml`

```yaml
combat:
  duration: 16

  bypass-requires-staffmode: true

  logout-kill: true

  untag-on-kill: true

  disable-elytra: false

  disable-fireworks: true

  crystal-pvp: true

  pearl-cooldown:
    enabled: true
    seconds: 5

  trident-cooldown:
    enabled: true
    seconds: 10

  lunge-cooldown:
    enabled: true
    seconds: 10

  safezone-block:
    enabled: true
    knockback: 0.4

  command-block:
    enabled: true
    mode: whitelist
    commands:
      - msg
      - pm
      - r
      - reply
```

## Leaving combat

A tag ends in one of four ways.

| Key | Default | What it does |
| --- | --- | --- |
| `duration` | `16` | Seconds a player stays tagged after dealing or taking PvP damage. Every new hit sets the timer back to the full duration. |
| `untag-on-kill` | `true` | The killer leaves combat the moment the player they were fighting dies. Bow and trident kills count, the shooter is the killer. The player who died is always untagged, with or without this option. |
| `logout-kill` | `true` | Quitting while tagged kills the player instead of letting them escape. |
| - | - | Dying always clears the tag. |

Turn `untag-on-kill` off if you want a survivor of a 2v1 to stay locked in combat: with it on,
the killer walks away free as soon as one opponent drops, even if a third player is still
fighting them (that player keeps their own tag either way).

The killer gets the `untag-on-kill` action bar from
[`messages.yml`](messages.md) plus the `expired` sound, the same one a tag that simply ran out
plays. Set the message to `""` for the sound only.
