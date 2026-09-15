# `economy/combat/messages.yml`

Location: `plugins/EconomyCore/economy/combat/messages.yml`

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

  # ── /combatmanager admin command ─────────────────────────────────────────
  combatmanager-usage:        "&cUsage: /combatmanager <tag|untag> <player|all> [duration]"
  combatmanager-usage-tag:    "&cUsage: /combatmanager tag <player> [duration]"
  combatmanager-usage-untag:  "&cUsage: /combatmanager untag <player|all>"
  # Placeholders: %input% (the raw argument that failed to resolve).
  combatmanager-player-offline: "&cPlayer &f%input%&c is not online."
  combatmanager-invalid-duration: "&cInvalid duration &f%input%&c. Examples: &f120&c, &f120s&c, &f3m&c, &f1h&c."
  # Placeholders: %player%, %time% (formatted duration string like "1m 30s").
  combatmanager-tagged:    "&#00A4FC&lADMIN &r&7» &fTagged &#00FC99%player%&f for &#00FC99%time%&f."
  # Placeholders: %count%
  combatmanager-untagged-all: "&#00A4FC&lADMIN &r&7» &fUntagged &#00FC99%count%&f player(s)."
  combatmanager-not-in-combat: "&#00A4FC&lADMIN &r&7» &#00FC99%player%&f is not in combat."
  combatmanager-untagged:  "&#00A4FC&lADMIN &r&7» &fUntagged &#00FC99%player%&f."
```
