# `economy/combat/messages.yml`

Location: `plugins/EconomyCore/economy/combat/messages.yml`

```yaml
messages:
  action-bar: "&fCombat: &#FC0000%time%"
  action-bar-pearl: "&fPearl: &#FC0000%time%"
  action-bar-trident: "&fTrident: &#FC0000%time%"
  action-bar-lunge: "&fLunge: &#FC0000%time%"
  action-bar-separator: "  "

  untag-on-kill: "&fCombat: &#00FC00ended"

  elytra-blocked: "&cYou cannot use elytra while in combat."

  firework-blocked: "&cYou cannot use fireworks while in combat."

  teleport-blocked: "&cYou cannot teleport while in combat."

  teleport-partner-blocked: "&c%player% is in combat."

  command-blocked: "&cYou cannot use this command while in combat."

  safezone-blocked: "&cYou cannot enter a safe zone while in combat."

  combatmanager-player-offline: "&cPlayer %input% is not online."
  combatmanager-invalid-duration: "&cInvalid duration %input%. Examples: 120, 120s, 3m, 1h."
  combatmanager-tagged:    "&#00A4FC&lADMIN &r&7» &fTagged &#00FC99%player%&f for &#00FC99%time%&f."
  combatmanager-untagged-all: "&#00A4FC&lADMIN &r&7» &fUntagged &#00FC99%count%&f player(s)."
  combatmanager-not-in-combat: "&#00A4FC&lADMIN &r&7» &#00FC99%player%&f is not in combat."
  combatmanager-untagged:  "&#00A4FC&lADMIN &r&7» &fUntagged &#00FC99%player%&f."
  combatmanager-mass-tagged: "&#00A4FC&lADMIN &r&7» &fTagged &#00FC99%count%&f of &#00FC99%total%&f online players for &#00FC99%time%&f."
  combatmanager-mass-empty:  "&cNobody is online."
```

`untag-on-kill` is the action bar the killer sees when
[`combat.untag-on-kill`](config.md) released their tag. Set it to `""` for no message; the
combat-expired sound still plays.
