# Announcement (`economy/announcement/`)

Broadcasted messages and repeated reminders.

## `economy/announcement/config.yml`

```yaml

sound: "minecraft:block.note_block.pling|0.7|1.2"

title:

  enabled: true

  text: "&#00A4FC&lANNOUNCE"

  subtitle: "&f%message%"

  fade-in: 250
  stay: 3500
  fade-out: 750

chat:

  enabled: true

  format: "&#00A4FC&lANNOUNCE &r&7» &f%message%"

reminders:

  stagger-seconds: 60
```

## `economy/announcement/reminder.yml`

```yaml

reminders:

  discord:
    interval-minutes: 20
    sound: "minecraft:entity.experience_orb.pickup|0.6|1.4"
    lines:
      - "           &#5865F2&lDISCORD"
      - ""
      - "&fJoin our &#5865F2Discord &fto chat with the community."
      - "&fGet &#5865F2support &fand hear about &#5865F2events &ffirst."
      - "&fEveryone is welcome, come say hi!"
      - ""
      - "        &#5865F2▶ discord.gg/yourserver ◀  "

  store:
    interval-minutes: 25
    sound: "minecraft:entity.experience_orb.pickup|0.6|1.4"
    lines:
      - "             &#00FC00&lSTORE"
      - ""
      - "&fSupport the server and grab &#00FC00ranks&f, &#00FC00keys &fand more."
      - "&fEvery purchase keeps the server &#00FC00online&f."
      - "&fThank you for helping the community grow."
      - ""
      - "         &#00FC00▶ store.yourserver.net ◀  "

  rules:
    interval-minutes: 30
    sound: "minecraft:entity.experience_orb.pickup|0.6|1.4"
    lines:
      - "             &#FCE300&lRULES"
      - ""
      - "&fPlay fair, no &#FCE300cheating&f. &#FCE300Griefing &fand &#FCE300scamming &fare allowed."
      - "&fBe respectful to everyone on the server."
      - "&fFull rules and punishments are listed &#FCE300in-game&f."
      - ""
      - "             &#FCE300▶ /rules ◀  "
```

