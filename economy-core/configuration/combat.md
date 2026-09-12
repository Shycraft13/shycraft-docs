# Combat (`economy/combat/`)

PvP combat tag: duration, restricted actions, action-bar timer.

## `economy/combat/config.yml`

```yaml
combat:

  duration: 16

  logout-kill: true

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

    knockback: 1.0

  command-block:
    enabled: true

    mode: whitelist

    commands:
      - msg
      - pm
      - r
      - reply
```

## `economy/combat/messages.yml`

```yaml
messages:

  action-bar: "&fCombat: &#FC0000%time%"
  action-bar-pearl: "&fPearl: &#FC0000%time%"
  action-bar-trident: "&fTrident: &#FC0000%time%"
  action-bar-lunge: "&fLunge: &#FC0000%time%"
  action-bar-separator: "  "

  elytra-blocked: "&cYou cannot use elytra while in combat."

  firework-blocked: "&cYou cannot use fireworks while in combat."

  command-blocked: "&cYou cannot use this command while in combat."

  safezone-blocked: "&cYou cannot enter a safe zone while in combat."
```

## `economy/combat/sounds.yml`

```yaml
sounds:

  expired: "minecraft:entity.experience_orb.pickup|1.0|1.0"

  combat-logged: "minecraft:entity.wither.spawn|0.6|1.8"
```

