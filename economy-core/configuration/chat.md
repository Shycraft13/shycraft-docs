# Chat (`economy/chat/`)

Global chat format, death messages and private messages.

## `economy/chat/chat.yml`

```yaml
CHAT:

  JOIN-LEAVE:
    ENABLE-JOIN-MESSAGES: true
    JOIN-MESSAGE: "&8[&a+&8] &7%player%"
    LEAVE-MESSAGE: "&8[&4-&8] &7%player%"

  FIRST-JOIN-MESSAGE:
    ENABLED: true
    LINES:
      - ""
      - "  &#00FC00&lNEW &r&7» &fWelcome &#00FC00%player% &fon &#00FC00EconomySMP.net"
      - "  &7#%unique_joins%"
      - ""

  GROUPS:
    owner:
      FORMAT: "%prefix% %name% &8» &d%message%"
    admin:
      FORMAT: "%prefix% %name% &8» &5%message%"
    default:
      FORMAT: "%prefix% %name% &8» &7%message%"

  LANGUAGE-FILTER:
    ENABLED: true

    ALLOWED-ALPHABETS:
      - "LATIN"
      - "NUMBERS"
      - "SYMBOLS"
    BLOCK-MESSAGE: "&cYour message contains characters that are not allowed on this server."

  ANTI-REPEAT:
    ENABLED: true
    BLOCK-MESSAGE: "&cDon't send the same message twice in a row."

  PING:
    ENABLED: true
    HIGHLIGHT: "&#FCE300@%player%"
    SOUND: "minecraft:entity.experience_orb.pickup|1.0|1.0"

  IGNORE:
    ENABLED: true
    MESSAGES:
      USAGE-IGNORE:   "&#FC0000Usage: /ignore <player>"
      USAGE-UNIGNORE: "&#FC0000Usage: /unignore <player>"
      SELF:           "&#FC0000You cannot ignore yourself."
      NOT-FOUND:      "&#FC0000Player not found."
      NOW-IGNORING:   "&#00A4FC&lIGNORE &r&7» &fYou are now ignoring &#FCE300%player%&f."
      NO-LONGER:      "&#00A4FC&lIGNORE &r&7» &fYou are no longer ignoring &#FCE300%player%&f."
      NOT-IGNORING:   "&#FC0000You are not ignoring &#FCE300%player%&#FC0000."
```

## `economy/chat/deathmessages.yml`

```yaml

SETTINGS:

  RADIUS: false
  CHUNKS: 5

MESSAGES:

  FALL:
    NORMAL: "&6☠ &6%player% &fhit the ground too hard."
    PVP: "&6☠ &6%player% &fwas doomed to fall by &6%killer%&f."
  VOID:
    NORMAL: "&6☠ &6%player% &ffell out of the world."
    PVP: "&6☠ &6%player% &fwas knocked into the void by &6%killer%&f."
  DROWNING:
    NORMAL: "&6☠ &6%player% &fforgot how to swim."
    PVP: "&6☠ &6%player% &fdrowned trying to escape &6%killer%&f."
  LAVA:
    NORMAL: "&6☠ &6%player% &ftried to swim in lava."
    PVP: "&6☠ &6%player% &fwas pushed into lava by &6%killer%&f."
  FIRE:
    NORMAL: "&6☠ &6%player% &fwent up in flames."
    PVP: "&6☠ &6%player% &fwas set ablaze by &6%killer%&f."
  FIRE-TICK:
    NORMAL: "&6☠ &6%player% &fburned to death."
    PVP: "&6☠ &6%player% &fwas burned to death by &6%killer%&f."
  HOT-FLOOR:
    NORMAL: "&6☠ &6%player% &fdiscovered the floor was lava."
    PVP: "&6☠ &6%player% &fwas forced onto magma by &6%killer%&f."
  SUFFOCATION: "&6☠ &6%player% &fsuffocated in a wall."
  CRAMMING: "&6☠ &6%player% &fwas squished too much."
  STARVATION: "&6☠ &6%player% &fstarved to death."
  FREEZE: "&6☠ &6%player% &ffroze to death."
  LIGHTNING: "&6☠ &6%player% &fwas struck by lightning."
  FALLING-BLOCK: "&6☠ &6%player% &fwas squashed by a falling block."
  FLY-INTO-WALL: "&6☠ &6%player% &fexperienced kinetic energy."
  DRAGON-BREATH: "&6☠ &6%player% &fwas roasted in dragon breath."
  MELTING: "&6☠ &6%player% &fmelted away."

  ENTITY-ATTACK:
    NORMAL: "&6☠ &6%player% &fwas slain."
    PVP: "&6☠ &6%player% &fwas slain by &6%killer%&f."
  ENTITY-SWEEP-ATTACK:
    NORMAL: "&6☠ &6%player% &fwas cut down."
    PVP: "&6☠ &6%player% &fwas cut down by &6%killer%&f."
  PROJECTILE:
    NORMAL: "&6☠ &6%player% &fwas shot down."
    PVP: "&6☠ &6%player% &fwas shot by &6%killer%&f."
  BLOCK-EXPLOSION:
    NORMAL: "&6☠ &6%player% &fblew up."
    PVP: "&6☠ &6%player% &fwas blown up by &6%killer%&f."
  ENTITY-EXPLOSION:
    NORMAL: "&6☠ &6%player% &fwas caught in an explosion."
    PVP: "&6☠ &6%player% &fwas blown up by &6%killer%&f."
  MAGIC:
    NORMAL: "&6☠ &6%player% &fwas killed by magic."
    PVP: "&6☠ &6%player% &fwas killed by &6%killer% &fusing magic."
  SONIC-BOOM:
    NORMAL: "&6☠ &6%player% &fwas obliterated by a sonic boom."
    PVP: "&6☠ &6%player% &fwas obliterated by &6%killer%&f."
  THORNS:
    NORMAL: "&6☠ &6%player% &fwas killed while trying to hurt something."
    PVP: "&6☠ &6%player% &fwas killed trying to hurt &6%killer%&f."
  CONTACT: "&6☠ &6%player% &fwas pricked to death."
  POISON: "&6☠ &6%player% &fsuccumbed to poison."
  WITHER: "&6☠ &6%player% &fwithered away."

  SUICIDE: "&6☠ &6%player% &fgave up."
  KILL: "&6☠ &6%player% &fwas killed."

  DEFAULT: "&6☠ &6%player% &fdied."
```

## `economy/chat/privatemessages.yml`

```yaml
PRIVATE-MESSAGES:
  OUTGOING-FORMAT: "&#00A4FC&lMSG &r&7» &fTo &#00FC99%player%&f: &7%message%"
  INCOMING-FORMAT: "&#00A4FC&lMSG &r&7» &fFrom &#00FC99%player%&f: &7%message%"
  PLAYER-NOT-FOUND: "&cPlayer not found or not online."
  SELF-MESSAGE: "&cYou cannot message yourself."
  DM-DISABLED: "&c%player% is not accepting private messages."
  NO-REPLY-TARGET: "&cNobody has messaged you yet."
```

## `economy/chat/sounds.yml`

```yaml
sounds:
  pm-send:    "minecraft:entity.chicken.egg|1.0|1.2"
  pm-receive: "minecraft:entity.chicken.egg|1.0|1.0"
```

