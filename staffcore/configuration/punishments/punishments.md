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
    reason: 'Cheating / Hacking'
    permission: staffcore.template.cheating
    expire-ladder: 90d
    ip-template: false
    ladder:
      fourth:
        duration: 30d
      third:
        duration: 15d
      second:
        duration: 7d
      first:
        duration: 3d

  xray:
    reason: 'XRay / ESP'
    permission: staffcore.template.xray
    expire-ladder: 90d
    ip-template: false
    ladder:
      fourth:
        duration: 30d
      third:
        duration: 15d
      second:
        duration: 7d
      first:
        duration: 3d

  exploiting:
    reason: 'Exploiting'
    permission: staffcore.template.exploiting
    expire-ladder: 90d
    ip-template: false
    ladder:
      fourth:
        duration: 30d
        message: |-
          &c&lFINAL WARNING BAN
          &7Reason: &f%reason%
          &7Expires in: &f%remaining%
          &7This is your 4th exploiting offence.
          &7Any further offence = &c&lpermanent ban&7.
        actions:
          - '/mute %player% 7d Follow-up mute for repeat exploiting.'
      third:
        duration: 15d
      second:
        duration: 7d
      first:
        duration: 3d

mute-templates:

  spam:
    reason: 'Spamming in chat'
    permission: staffcore.template.spam
    expire-ladder: 90d
    ip-template: false
    ladder:
      fourth:
        duration: 8h
      third:
        duration: 5h
      second:
        duration: 1h
      first:
        message: '&#F97603Please stop spamming! This is your first warning. Continue and you will be muted for 1 hour.'
        duration: 5s

  threats:
    reason: 'Real-life threats'
    permission: staffcore.template.threats
    expire-ladder: 90d
    ip-template: false
    ladder:
      fourth:
        duration: 3d
        actions:
          - '/warn %player% Escalated threats — recorded warn.'
      third:
        duration: 1d
      second:
        duration: 12h
      first:
        duration: 6h

  advertising:
    reason: 'Advertising other servers'
    permission: staffcore.template.advertising
    expire-ladder: 90d
    ip-template: false
    ladder:
      fourth:
        duration: 3d
      third:
        duration: 1d
      second:
        duration: 12h
      first:
        duration: 6h

warn-templates:

  minor-spam:
    reason: 'Spamming (minor)'
    permission: staffcore.template.minorspam
    expire-ladder: 90d
    ip-template: false
    ladder:
      fourth:
        actions:
          - '/mute %player% 1h Repeated spam after warnings.'
      third:
        actions:
          - '/mute %player% 30m Repeated spam after warnings.'
      second: {}
      first: {}

kick-templates:

  behavior:
    reason: 'Unacceptable behaviour'
    permission: staffcore.template.behavior
    expire-ladder: 90d
    ip-template: false
    ladder:
      fourth:
        actions:
          - '/ban %player% 1d Repeated bad behaviour, 1d ban.'
      third:
        actions:
          - '/mute %player% 3h'
      second:
        actions:
          - '/mute %player% 30m'
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
