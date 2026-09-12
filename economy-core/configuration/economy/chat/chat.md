# `economy/chat/chat.yml`

Location: `plugins/EconomyCore/economy/chat/chat.yml`

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
