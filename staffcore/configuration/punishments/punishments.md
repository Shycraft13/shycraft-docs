# `punishments/punishments.yml`

Location: `plugins/StaffCore/punishments/punishments.yml`

The template catalogue. Each category has its own top-level section; every
template inside picks up the primary action from its section (ban-templates
always ban, mute-templates always mute, etc.).

See [Punishment Templates](../../templates.md) for the full model
walkthrough and field reference.

```yaml
ban-templates:

  cheating:
    reason: 'Using a modified client for unfair advantages'
    permission: staffcore.template.ban.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 90d
      third:
        duration: 30d
      second:
        duration: 14d
      first:
        duration: 5d

  autoclicker:
    reason: 'Autoclicker abuse'
    permission: staffcore.template.ban.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 90d
      third:
        duration: 30d
      second:
        duration: 14d
      first:
        duration: 5d

  macros:
    reason: 'Using macros or automated scripts'
    permission: staffcore.template.ban.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 60d
      third:
        duration: 21d
      second:
        duration: 7d
      first:
        duration: 3d

  baritone:
    reason: 'Using Baritone or another pathfinding bot'
    permission: staffcore.template.ban.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 60d
      third:
        duration: 21d
      second:
        duration: 7d
      first:
        duration: 3d

  xray-pack:
    reason: 'Using an x-ray resource pack for ore detection'
    permission: staffcore.template.ban.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 90d
      third:
        duration: 30d
      second:
        duration: 14d
      first:
        duration: 7d

  esp:
    reason: 'Using an ESP mod'
    permission: staffcore.template.ban.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 90d
      third:
        duration: 30d
      second:
        duration: 14d
      first:
        duration: 5d

  bug-abuse:
    reason: 'Abusing an unreported bug for personal gain'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      fourth:
        duration: 90d
      third:
        duration: 30d
      second:
        duration: 14d
      first:
        duration: 7d

  duping:
    reason: 'Duplication method / duped items'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      fourth:
        duration: 90d
        actions:
          - '/warn %player% Duping ladder tier 4, inventory reviewed by staff.'
      third:
        duration: 30d
      second:
        duration: 14d
      first:
        duration: 7d

  seed-abuse:
    reason: 'Seed finding / using an obtained seed'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      fourth:
        duration: 60d
      third:
        duration: 21d
      second:
        duration: 7d
      first:
        duration: 3d

  irl-trading:
    reason: 'Trading in-game items for real money'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      third:
        duration: 90d
      second:
        duration: 30d
      first:
        duration: 14d

  cross-server-trading:
    reason: 'Trading items across different servers'
    permission: staffcore.template.ban.basic
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 30d
      third:
        duration: 14d
      second:
        duration: 5d
      first:
        duration: 2d

  alt-limit:
    reason: 'Running more than 5 alt accounts'
    permission: staffcore.template.ban.basic
    expire-ladder: 365d
    ladder:
      first:
        duration: 30d

  alt-abuse:
    reason: 'Using alt accounts to gain unfair advantages'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      fourth:
        duration: 90d
      third:
        duration: 30d
      second:
        duration: 14d
      first:
        duration: 5d

  ban-evasion:
    reason: 'Ban evasion with an alt account'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      third:
        duration: 90d
      second:
        duration: 30d
      first:
        duration: 14d
        actions:
          - '/warn %player% Ban evasion, parent account reviewed by staff.'

  staff-impersonation:
    reason: 'Impersonating a staff member'
    permission: staffcore.template.ban.basic
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 30d
      third:
        duration: 14d
      second:
        duration: 5d
      first:
        duration: 1d

  staff-disrespect:
    reason: 'Repeated disrespect / abuse of staff'
    permission: staffcore.template.ban.basic
    expire-ladder: 90d
    ladder:
      fourth:
        duration: 30d
      third:
        duration: 14d
      second:
        duration: 5d
      first:
        duration: 1d

  lying-to-staff:
    reason: 'Lying to staff during an investigation'
    permission: staffcore.template.ban.basic
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 30d
        actions:
          - '/warn %player% Repeated dishonesty with staff, next offence escalates.'
      third:
        duration: 14d
      second:
        duration: 5d
      first:
        duration: 2d

  chargeback:
    reason: 'Store chargeback / payment fraud'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      first:
        duration: permanent

  slurs-ban:
    reason: 'Slurs / hate speech'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      third:
        duration: permanent
      second:
        duration: 30d
      first:
        duration: 7d

  racism:
    reason: 'Racist behaviour or language'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      third:
        duration: permanent
      second:
        duration: 30d
      first:
        duration: 7d

  discrimination:
    reason: 'Discrimination against a group of people'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      third:
        duration: permanent
      second:
        duration: 30d
      first:
        duration: 7d

  nazi-content:
    reason: 'Sharing nazi or extremist content'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      first:
        duration: permanent

  threats:
    reason: 'Death threats against another player'
    permission: staffcore.template.ban.severe
    expire-ladder: 365d
    ladder:
      third:
        duration: permanent
      second:
        duration: 60d
      first:
        duration: 14d

  harassment:
    reason: 'Harassment of another player'
    permission: staffcore.template.ban.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: permanent
      third:
        duration: 60d
      second:
        duration: 14d
      first:
        duration: 5d

  doxxing:
    reason: 'Sharing private info / doxxing'
    permission: staffcore.template.admin
    expire-ladder: 3650d
    ip-template: true
    ladder:
      first:
        duration: permanent

  ddos-threat:
    reason: 'DDoS threats or real-world threats'
    permission: staffcore.template.admin
    expire-ladder: 3650d
    ip-template: true
    ladder:
      first:
        duration: permanent

  cp-content:
    reason: 'Sharing illegal content on the server'
    permission: staffcore.template.admin
    expire-ladder: 3650d
    ip-template: true
    ladder:
      first:
        duration: permanent

  ban-evasion-permanent:
    reason: 'Evading a permanent ban with alt accounts'
    permission: staffcore.template.admin
    expire-ladder: 3650d
    ip-template: true
    ladder:
      first:
        duration: permanent

  mass-alt:
    reason: 'Confirmed mass-alt spam / farm ring'
    permission: staffcore.template.admin
    expire-ladder: 3650d
    ip-template: true
    ladder:
      first:
        duration: permanent

mute-templates:

  spam:
    reason: 'Spamming messages in public chat'
    permission: staffcore.template.mute.basic
    expire-ladder: 30d
    ladder:
      fourth:
        duration: 12h
      third:
        duration: 4h
      second:
        duration: 1h
        actions:
          - '/warn %player% Repeat chat spam.'
      first:
        duration: 10m

  caps:
    reason: 'Using excessive caps in chat'
    permission: staffcore.template.mute.basic
    expire-ladder: 30d
    ladder:
      fourth:
        duration: 2h
      third:
        duration: 30m
      second:
        duration: 10m
      first:
        duration: 5m

  begging:
    reason: 'Begging for items, money or ranks'
    permission: staffcore.template.mute.basic
    expire-ladder: 30d
    ladder:
      fourth:
        duration: 1d
      third:
        duration: 6h
      second:
        duration: 1h
      first:
        duration: 15m

  off-topic:
    reason: 'Persistent off-topic messages in main chat'
    permission: staffcore.template.mute.basic
    expire-ladder: 30d
    ladder:
      fourth:
        duration: 4h
      third:
        duration: 1h
      second:
        duration: 15m
      first:
        duration: 5m

  advertising-mute:
    reason: 'Advertising another server or community'
    permission: staffcore.template.mute.basic
    expire-ladder: 60d
    ladder:
      fourth:
        duration: 7d
        actions:
          - '/warn %player% Repeat advertising, next offence may escalate to a ban.'
      third:
        duration: 1d
      second:
        duration: 6h
      first:
        duration: 1h

  drama:
    reason: 'Fueling drama in main chat'
    permission: staffcore.template.mute.basic
    expire-ladder: 60d
    ladder:
      fourth:
        duration: 1d
      third:
        duration: 6h
      second:
        duration: 1h
      first:
        duration: 30m

  argument:
    reason: 'Ongoing public argument after being told to stop'
    permission: staffcore.template.mute.basic
    expire-ladder: 30d
    ladder:
      fourth:
        duration: 6h
      third:
        duration: 1h
      second:
        duration: 15m
      first:
        duration: 5m

  toxicity-minor:
    reason: 'Minor toxicity / rude behaviour'
    permission: staffcore.template.mute.basic
    expire-ladder: 60d
    ladder:
      fourth:
        duration: 1d
      third:
        duration: 6h
      second:
        duration: 2h
      first:
        duration: 30m

  toxicity-severe:
    reason: 'Toxic behaviour / repeated hostility'
    permission: staffcore.template.mute.severe
    expire-ladder: 90d
    ladder:
      fourth:
        duration: 30d
        actions:
          - '/warn %player% Repeat severe toxicity, next offence may escalate to a ban.'
      third:
        duration: 7d
      second:
        duration: 1d
      first:
        duration: 6h

  disrespect-staff:
    reason: 'Disrespectful behaviour towards staff'
    permission: staffcore.template.mute.basic
    expire-ladder: 60d
    ladder:
      fourth:
        duration: 1d
      third:
        duration: 6h
      second:
        duration: 2h
      first:
        duration: 30m

  lying-to-staff-mute:
    reason: 'Lying to staff during an investigation'
    permission: staffcore.template.mute.basic
    expire-ladder: 60d
    ladder:
      fourth:
        duration: 1d
      third:
        duration: 3h
      second:
        duration: 30m
      first:
        duration: 10m

  false-accusation:
    reason: 'Publicly accusing players without proof'
    permission: staffcore.template.mute.basic
    expire-ladder: 60d
    ladder:
      fourth:
        duration: 1d
      third:
        duration: 6h
      second:
        duration: 1h
      first:
        duration: 15m

  impersonation:
    reason: 'Impersonating other players in chat'
    permission: staffcore.template.mute.basic
    expire-ladder: 90d
    ladder:
      fourth:
        duration: 3d
      third:
        duration: 1d
      second:
        duration: 6h
      first:
        duration: 1h

  slurs:
    reason: 'Use of slurs / hateful language'
    permission: staffcore.template.mute.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 365d
        actions:
          - '/warn %player% Zero-tolerance slur policy, escalated to top mute tier.'
      third:
        duration: 30d
      second:
        duration: 7d
      first:
        duration: 1d

  racism-mute:
    reason: 'Racist behaviour in chat'
    permission: staffcore.template.mute.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 365d
      third:
        duration: 30d
      second:
        duration: 7d
      first:
        duration: 1d

  discrimination-mute:
    reason: 'Discriminatory language in chat'
    permission: staffcore.template.mute.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 365d
      third:
        duration: 30d
      second:
        duration: 7d
      first:
        duration: 1d

  threats-mute:
    reason: 'Death threats made in chat'
    permission: staffcore.template.mute.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 365d
      third:
        duration: 30d
        actions:
          - '/warn %player% Repeat threats, next offence escalates.'
      second:
        duration: 7d
      first:
        duration: 1d

  harassment-mute:
    reason: 'Harassing another player through chat'
    permission: staffcore.template.mute.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 365d
      third:
        duration: 30d
      second:
        duration: 7d
      first:
        duration: 1d

  nsfw-chat:
    reason: 'NSFW / sexually explicit chat'
    permission: staffcore.template.mute.severe
    expire-ladder: 90d
    ladder:
      fourth:
        duration: 30d
      third:
        duration: 7d
      second:
        duration: 1d
      first:
        duration: 6h

  mic-spam:
    reason: 'Mic spam / non-stop talking'
    permission: staffcore.template.mute.basic
    expire-ladder: 30d
    ladder:
      fourth:
        duration: 12h
      third:
        duration: 3h
      second:
        duration: 1h
      first:
        duration: 15m

  soundboard:
    reason: 'Soundboard / audio player abuse'
    permission: staffcore.template.mute.basic
    expire-ladder: 60d
    ladder:
      fourth:
        duration: 3d
      third:
        duration: 1d
      second:
        duration: 6h
      first:
        duration: 1h

  ear-rape:
    reason: 'Ear-rape / loud audio / mic boost'
    permission: staffcore.template.mute.basic
    expire-ladder: 60d
    ladder:
      fourth:
        duration: 3d
      third:
        duration: 1d
      second:
        duration: 6h
      first:
        duration: 1h

  music-in-voice:
    reason: 'Playing music in voice chat'
    permission: staffcore.template.mute.basic
    expire-ladder: 30d
    ladder:
      fourth:
        duration: 12h
      third:
        duration: 3h
      second:
        duration: 30m
      first:
        duration: 10m

  voice-toxicity:
    reason: 'Toxic behaviour in voice chat'
    permission: staffcore.template.mute.basic
    expire-ladder: 60d
    ladder:
      fourth:
        duration: 1d
      third:
        duration: 6h
      second:
        duration: 2h
      first:
        duration: 30m

  voice-slurs:
    reason: 'Using slurs in voice chat'
    permission: staffcore.template.mute.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 365d
        actions:
          - '/warn %player% Zero-tolerance voice-slur policy, top mute tier.'
      third:
        duration: 30d
      second:
        duration: 7d
      first:
        duration: 1d

  voice-threats:
    reason: 'Making threats through voice chat'
    permission: staffcore.template.mute.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 365d
      third:
        duration: 30d
      second:
        duration: 7d
      first:
        duration: 1d

  voice-harassment:
    reason: 'Harassing another player through voice chat'
    permission: staffcore.template.mute.severe
    expire-ladder: 180d
    ladder:
      fourth:
        duration: 365d
      third:
        duration: 30d
      second:
        duration: 7d
      first:
        duration: 1d

  voice-nsfw:
    reason: 'NSFW / sexually explicit voice chat'
    permission: staffcore.template.mute.severe
    expire-ladder: 90d
    ladder:
      fourth:
        duration: 30d
      third:
        duration: 7d
      second:
        duration: 1d
      first:
        duration: 6h

  voice-impersonation:
    reason: 'Impersonating players / staff via voice'
    permission: staffcore.template.mute.basic
    expire-ladder: 90d
    ladder:
      fourth:
        duration: 3d
      third:
        duration: 1d
      second:
        duration: 6h
      first:
        duration: 1h

  chat-flood:
    reason: 'Automated chat flooding by a bot'
    permission: staffcore.template.admin
    expire-ladder: 90d
    ladder:
      first:
        duration: permanent

warn-templates:

  minor-spam:
    reason: 'Minor chat spam — first warning'
    permission: staffcore.template.warn.basic
    expire-ladder: 30d
    ladder:
      fourth:
        actions:
          - '/mute %player% 1h Repeat spam despite warnings.'
      third:
        actions:
          - '/mute %player% 15m Repeat spam despite warnings.'
      second: {}
      first: {}

  minor-caps:
    reason: 'Excessive caps in chat — first warning'
    permission: staffcore.template.warn.basic
    expire-ladder: 30d
    ladder:
      fourth:
        actions:
          - '/mute %player% 30m Repeat caps despite warnings.'
      third: {}
      second: {}
      first: {}

  begging-warn:
    reason: 'Begging for items, money or ranks'
    permission: staffcore.template.warn.basic
    expire-ladder: 30d
    ladder:
      fourth:
        actions:
          - '/mute %player% 1h Repeat begging after warnings.'
      third: {}
      second: {}
      first: {}

  off-topic-warn:
    reason: 'Persistent off-topic messages in main chat'
    permission: staffcore.template.warn.basic
    expire-ladder: 30d
    ladder:
      fourth:
        actions:
          - '/mute %player% 30m Repeat off-topic despite warnings.'
      third: {}
      second: {}
      first: {}

  drama-warn:
    reason: 'Fueling drama in public chat'
    permission: staffcore.template.warn.basic
    expire-ladder: 60d
    ladder:
      fourth:
        actions:
          - '/mute %player% 3h Repeat drama despite warnings.'
      third:
        actions:
          - '/mute %player% 30m Repeat drama despite warnings.'
      second: {}
      first: {}

  advertising-warn:
    reason: 'Mentioning other servers in chat'
    permission: staffcore.template.warn.basic
    expire-ladder: 90d
    ladder:
      fourth:
        actions:
          - '/mute %player% 12h Repeat advertising, next offence may be a ban.'
      third:
        actions:
          - '/mute %player% 1h Repeat advertising.'
      second: {}
      first: {}

  minor-toxicity:
    reason: 'Rude / mildly toxic behaviour'
    permission: staffcore.template.warn.basic
    expire-ladder: 60d
    ladder:
      fourth:
        actions:
          - '/mute %player% 2h Repeat rude behaviour after warnings.'
      third:
        actions:
          - '/mute %player% 30m Repeat rude behaviour after warnings.'
      second: {}
      first: {}

  disrespect-warn:
    reason: 'Disrespect towards staff or other players'
    permission: staffcore.template.warn.basic
    expire-ladder: 60d
    ladder:
      fourth:
        actions:
          - '/mute %player% 3h Repeat disrespect after warnings.'
      third:
        actions:
          - '/mute %player% 30m Repeat disrespect after warnings.'
      second: {}
      first: {}

  false-accusation-warn:
    reason: 'Publicly accusing players without proof'
    permission: staffcore.template.warn.basic
    expire-ladder: 60d
    ladder:
      fourth:
        actions:
          - '/mute %player% 1h Repeat false accusations after warnings.'
      third: {}
      second: {}
      first: {}

  lying-warn:
    reason: 'Being dishonest with staff — first warning'
    permission: staffcore.template.warn.basic
    expire-ladder: 60d
    ladder:
      fourth:
        actions:
          - '/mute %player% 2h Repeat dishonesty after warnings.'
      third: {}
      second: {}
      first: {}

  voice-warning:
    reason: 'Voice chat behaviour warning'
    permission: staffcore.template.warn.basic
    expire-ladder: 30d
    ladder:
      fourth:
        actions:
          - '/mute %player% 1h Repeat voice chat issues after warnings.'
      third:
        actions:
          - '/mute %player% 15m Repeat voice chat issues after warnings.'
      second: {}
      first: {}

  voice-music-warn:
    reason: 'Playing music in voice chat'
    permission: staffcore.template.warn.basic
    expire-ladder: 30d
    ladder:
      fourth:
        actions:
          - '/mute %player% 30m Repeat music-in-voice after warnings.'
      third: {}
      second: {}
      first: {}

  voice-loud-warn:
    reason: 'Voice too loud / mic-boost'
    permission: staffcore.template.warn.basic
    expire-ladder: 30d
    ladder:
      fourth:
        actions:
          - '/mute %player% 1h Repeat loud voice after warnings.'
      third: {}
      second: {}
      first: {}

  suspected-cheats:
    reason: 'Suspicious combat behaviour'
    permission: staffcore.template.warn.basic
    expire-ladder: 90d
    ladder:
      fourth:
        actions:
          - '/kick %player% Repeated combat pattern flagged.'
      third: {}
      second: {}
      first: {}

  suspected-autoclicker:
    reason: 'Suspicious clicking pattern flagged'
    permission: staffcore.template.warn.basic
    expire-ladder: 60d
    ladder:
      fourth:
        actions:
          - '/kick %player% Repeat suspicious clicking, please review.'
      third: {}
      second: {}
      first: {}

  suspected-bug-abuse:
    reason: 'Possible unreported bug abuse'
    permission: staffcore.template.warn.basic
    expire-ladder: 90d
    ladder:
      fourth:
        actions:
          - '/kick %player% Repeat bug-abuse flag.'
      third: {}
      second: {}
      first: {}

  suspected-duping:
    reason: 'Suspicious item stacks flagged for review'
    permission: staffcore.template.warn.basic
    expire-ladder: 90d
    ladder:
      fourth:
        actions:
          - '/kick %player% Repeat duping flag, inventory reviewed by staff.'
      third: {}
      second: {}
      first: {}

  suspected-seed:
    reason: 'Suspicious world-gen knowledge'
    permission: staffcore.template.warn.basic
    expire-ladder: 90d
    ladder:
      fourth:
        actions:
          - '/kick %player% Repeat seed-tool flag.'
      third: {}
      second: {}
      first: {}

kick-templates:

  behavior:
    reason: 'Unacceptable behaviour on the server'
    permission: staffcore.template.kick.basic
    expire-ladder: 30d
    ladder:
      fourth:
        actions:
          - '/mute %player% 6h Repeat unacceptable behaviour.'
          - '/warn %player% 4th behaviour offence, next step is a ban.'
      third:
        actions:
          - '/mute %player% 2h'
      second:
        actions:
          - '/mute %player% 30m'
      first: {}

  afk-kick:
    reason: 'AFK — come back to play actively'
    permission: staffcore.template.kick.basic
    expire-ladder: 7d
    ladder:
      first: {}

  cooldown:
    reason: 'Take a break from chat / cool down'
    permission: staffcore.template.kick.basic
    expire-ladder: 7d
    ladder:
      fourth:
        actions:
          - '/mute %player% 30m Repeated escalation, chat cooldown.'
      third: {}
      second: {}
      first: {}

  argument-kick:
    reason: 'Cool down and step away from the argument'
    permission: staffcore.template.kick.basic
    expire-ladder: 7d
    ladder:
      fourth:
        actions:
          - '/mute %player% 1h Repeat arguments after kicks.'
      third: {}
      second: {}
      first: {}

  disruption:
    reason: 'Disruptive gameplay bothering other players'
    permission: staffcore.template.kick.basic
    expire-ladder: 30d
    ladder:
      fourth:
        actions:
          - '/mute %player% 1h Repeat disruption despite kicks.'
      third: {}
      second: {}
      first: {}

  unsupported-client:
    reason: 'Modified client — rejoin on a clean client'
    permission: staffcore.template.kick.basic
    expire-ladder: 7d
    ladder:
      first: {}

  suspicious-behavior:
    reason: 'Suspicious behaviour — please rejoin normally'
    permission: staffcore.template.kick.basic
    expire-ladder: 30d
    ladder:
      fourth:
        actions:
          - '/warn %player% Repeat suspicious behaviour, please review.'
      third: {}
      second: {}
      first: {}

  possible-alt:
    reason: 'Possible alt account — please switch to your main'
    permission: staffcore.template.kick.basic
    expire-ladder: 30d
    ladder:
      first: {}

  test-account:
    reason: 'Test / duplicate account kick'
    permission: staffcore.template.admin
    expire-ladder: 30d
    ladder:
      first: {}

  boot-off:
    reason: 'Removed from server pending review'
    permission: staffcore.template.admin
    expire-ladder: 30d
    ladder:
      first: {}
```

## Field reference

| Field | Description |
| --- | --- |
| `reason` | Default reason if the ladder step doesn't override. |
| `permission` | Permission required to use this template. Fallback: `staffcore.admin`. |
| `expire-ladder` | How long past applications count toward the tier counter. `0` = never expire. |
| `ip-template` | Reserved; currently parsed but not enforced. |
| `ladder.<step>.duration` | Punishment length (ban / mute only). |
| `ladder.<step>.reason` | Overrides the template-level reason for this tier. |
| `ladder.<step>.message` | Multi-line screen shown to the target when this tier fires. |
| `ladder.<step>.actions` | Extra console commands run in addition to the primary action. |

Ladder steps are named `first`, `second`, `third`, ..., `tenth`. Order in the
file doesn't matter (the plugin sorts canonically). Empty steps (`first: {}`)
are allowed and apply the template-level defaults.

## Placeholders

Every reason, message and action supports:

`%player%`, `%staff%`, `%reason%`, `%duration%`, `%expires%`, `%remaining%`,
`%date%`, `%template%`, `%tier%`.

## Reloading

Run `/staffcore reload` after editing to rebuild the template catalogue
without restarting the server. Existing usage rows in the database are not
affected.
