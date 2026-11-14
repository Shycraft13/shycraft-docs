# `economy/rtpqueue/config.yml`

Location: `plugins/EconomyCore/economy/rtpqueue/config.yml`

```yaml
countdown-seconds: 5

spawn-distance: 3

search-attempts: 15

MASS-QUEUE:
  ENABLED: false
  INTERVAL: "1h"
  WAIT-SECONDS: 60
  REMINDERS: [30, 10]
  MIN-PLAYERS: 2
  WORLD: world
  SPACING: 3
  MAX-RADIUS: 32

DUEL:
  ENABLED: false
  REQUEST-SECONDS: 60
  REQUEST-COOLDOWN-SECONDS: 30

WORLD-SETTINGS:
  world:
    MAX-RADIUS: 5000
    MIN-RADIUS: 500
    CENTER-X: 0
    CENTER-Z: 0
  world_nether:
    MAX-RADIUS: 500
    MIN-RADIUS: 50
    CENTER-X: 0
    CENTER-Z: 0
  world_the_end:
    MAX-RADIUS: 2000
    MIN-RADIUS: 150
    CENTER-X: 0
    CENTER-Z: 0
```
