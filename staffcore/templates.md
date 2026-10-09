# Punishment Templates

Templates are pre-defined punishments with a tier ladder. Instead of typing `/ban Steve 3d Cheating` for a first offence and `/ban Steve 30d Cheating` for a fourth, you configure the whole progression once and let staff apply `/punish Steve cheating` for every offence. The plugin picks the right tier automatically.

Templates live under `punishments/punishments.yml` and are grouped by category. See [Placeholders](#placeholders) for the full placeholder set.

## The four categories

Every template belongs to exactly one category, and the category is fixed by which top-level YAML key it sits under in `punishments/punishments.yml`:

| Category | Section | Primary action |
| --- | --- | --- |
| Ban  | `ban-templates:` | Bans the player. `duration:` becomes the ban length. |
| Mute | `mute-templates:` | Mutes the player. `duration:` becomes the mute length. |
| Warn | `warn-templates:` | Adds a warn to the player's history. `duration:` is ignored. |
| Kick | `kick-templates:` | Kicks the player. `duration:` is ignored. |

You can't put a `duration` on a warn/kick template and expect it to do something; the category dictates the action.

## Template fields

```yaml
ban-templates:
  cheating:                             # template name (used in /punish <player> cheating)
    reason: 'Cheating / Hacking'         # default reason if the ladder step doesn't override
    permission: staffcore.template.cheating
    expire-ladder: 90d                   # past usages older than this don't count for tier progression
    ip-template: false                   # parsed but not yet enforced
    ladder:
      first:
        duration: 3d
      second:
        duration: 7d
      third:
        duration: 15d
        reason: 'Cheating — 3rd offence'
      fourth:
        duration: 30d
        message: |-
          &c&lFINAL WARNING BAN
          &7This is your 4th offence.
        actions:
          - '/mute %player% 7d Follow-up mute for repeat offence.'
```

| Field | Description |
| --- | --- |
| `reason` | Default reason if the ladder step doesn't specify its own. Also used as the fallback in the `/punish` picker. |
| `permission` | Permission required to apply this template. Recommended pattern: `staffcore.template.<name>`. |
| `expire-ladder` | How long a past usage of this template counts toward the tier. Format is the same as the command's time argument (`90d`, `2w`, `permanent`, etc.). `0` = never expire. |
| `ip-template` | Reserved. Currently accepted but not enforced. |
| `ladder:` | Named steps (`first`, `second`, `third`, ..., `tenth`). Order in the YAML doesn't matter; the plugin sorts canonically. |

### Ladder step fields

Each ladder step is an optional map. Every field is optional:

| Field | Description |
| --- | --- |
| `duration` | The primary action's length. Only meaningful for ban and mute categories. |
| `reason` | Overrides the template-level `reason` when this tier fires. |
| `message` | Overrides the disconnect / target-notify screen when this tier fires. Multi-line. |
| `actions` | List of console commands to run in addition to the primary action. Any command works. Placeholders are substituted before dispatch. |

Empty steps are allowed (`first: {}`); they simply apply the primary action with the template-level defaults.

## Tier progression

When staff runs `/punish Steve cheating`:

1. The plugin counts prior applications of the `cheating` template on Steve that are **not older than `expire-ladder`** and **not voided** (see below).
2. Count → tier: 0 → `first`, 1 → `second`, 2 → `third`, ..., 9 → `tenth`. Beyond `tenth` the last-defined step is repeated.
3. If the tier's step is missing (e.g. you only defined `first` and `third`), the plugin walks downward and uses the highest defined step at or below the target tier.
4. The primary action fires with the resolved `duration`, `reason` and `message`.
5. Every `actions:` command runs.
6. A new usage row is inserted so the next `/punish` sees the increased count.

## Voiding a usage

If staff apply a template by mistake and undo it with `/unban Steve --void` or `/unwarn Steve <id> --void`, the newest matching usage row is voided (a `voided_at` + `voided_by` stamp is written). Voided rows are still visible in `/history` but are ignored by the tier counter, so the next real offence starts from the correct tier.

Ordinary `/unban Steve` (no `--void`) is a "he served his time" removal: the ban lifts but the usage still counts toward the ladder.

## Broadcasts

Templates broadcast on the same `staffcore.notify` channel as the corresponding raw command. The broadcast messages live under `template:` in `punishments/messages.yml` (`template.broadcast`, `template.applied`).

## Placeholders

Every message, screen and `actions` line supports the same placeholder set:

| Placeholder | Meaning |
| --- | --- |
| `%player%` | Target name |
| `%staff%` | Staff member who applied the punishment |
| `%reason%` | Effective reason (step override beats template default) |
| `%duration%` | Human-readable duration (e.g. `1d 12h`) or the label from `time.permanent-label` |
| `%expires%` | Absolute expiry timestamp |
| `%remaining%` | Time remaining before the punishment expires |
| `%date%` | Date the punishment was applied |
| `%template%` | Template name |
| `%tier%` | 1-based tier index of the applied step |

Placeholders use `%name%` syntax everywhere.

## Shipped defaults

The default template set is aligned **1:1 with the in-game `/rules` menu**. Griefing, stealing and scamming are legitimate SMP gameplay and have no templates.

Voice-chat templates use the mute action — a mute silences both the target's chat AND their Simple Voice Chat microphone (when SVC is installed and `punishments/config.yml`'s `mute.voicechat.enabled: true`, which is the default).

**Ban templates — Server Rules:**

- *Client cheats (severe tier)*: `cheating` (catch-all for hacked clients, movement mods, inventory mods, health indicators, radar, freecam, auto-place, easy-place, mouse tweaks, crafting modifications and every other modified-client cheat), `autoclicker`, `macros`, `baritone`, `xray-pack`
- *Integrity (severe tier)*: `bug-abuse`, `duping`, `seed-abuse`, `irl-trading`
- *Cross-server*: `cross-server-trading` (basic tier)
- *Alts (Server Rule: max 5 accounts)*: `alt-limit` (basic tier), `alt-abuse`, `ban-evasion` (severe tier)

**Ban templates — Community / Chat Rules:**

- *Staff*: `staff-impersonation`, `staff-disrespect`, `lying-to-staff` (basic tier)
- *Payment*: `chargeback` (severe tier, straight permaban)
- *Hate / threats (severe tier)*: `slurs-ban`, `racism`, `discrimination`, `nazi-content` (straight permaban), `threats`, `harassment`
- *Admin-only (permanent + IP scope)*: `doxxing`, `ddos-threat`, `cp-content`, `ban-evasion-permanent`, `mass-alt`

**Mute templates:**

- *Chat noise (basic tier)*: `spam`, `caps`, `begging`, `off-topic`, `advertising-mute`, `drama`, `argument`
- *Social offences*: `toxicity-minor`, `disrespect-staff`, `lying-to-staff-mute`, `false-accusation`, `impersonation` (basic tier); `toxicity-severe` (severe tier)
- *Hate / severe (severe tier)*: `slurs`, `racism-mute`, `discrimination-mute`, `threats-mute`, `harassment-mute`, `nsfw-chat`
- *Voice chat (basic tier)*: `mic-spam`, `soundboard`, `ear-rape`, `music-in-voice`, `voice-toxicity`, `voice-impersonation`
- *Voice chat (severe tier)*: `voice-slurs`, `voice-threats`, `voice-harassment`, `voice-nsfw`
- *Admin-only*: `chat-flood`

**Warn templates (basic tier):**

- *Chat rules*: `minor-spam`, `minor-caps`, `begging-warn`, `off-topic-warn`, `drama-warn`, `advertising-warn`
- *Social*: `minor-toxicity`, `disrespect-warn`, `false-accusation-warn`, `lying-warn`
- *Voice chat*: `voice-warning`, `voice-music-warn`, `voice-loud-warn`
- *Integrity soft checks*: `suspected-cheats`, `suspected-autoclicker`, `suspected-bug-abuse`, `suspected-duping`, `suspected-seed`

**Kick templates (basic tier):**

- *Cool-downs / disruption*: `behavior`, `afk-kick`, `cooldown`, `argument-kick`, `disruption`
- *Integrity*: `unsupported-client`, `suspicious-behavior`, `possible-alt`
- *Admin-only*: `test-account`, `boot-off`

See [`punishments/punishments.yml`](configuration/punishments/punishments.md) for the full text with ladder progressions. Delete the whole file to start from scratch; it regenerates on next start if missing.

## Permissions and templates

Templates share permission nodes on purpose so an operator only has to grant a small number of buckets rather than one line per template.

| Bucket | Templates it unlocks |
| --- | --- |
| `staffcore.template.ban.basic` | Everyday ban templates (griefing, scamming, ...) |
| `staffcore.template.ban.severe` | Long / permanent bans (cheating, xray, threats, ...) |
| `staffcore.template.mute.basic` | Everyday mute templates (spam, caps, ...) |
| `staffcore.template.mute.severe` | Long-form mute templates (slurs, threats, ...) |
| `staffcore.template.warn.basic` | Every warn template |
| `staffcore.template.kick.basic` | Every kick template |
| `staffcore.template.admin` | Permaban / IP-scope templates (doxxing, ban-evasion, ...) |

Typical wiring:

- **helper** → `ban.basic`, `mute.basic`, `warn.basic`, `kick.basic`
- **mod** → helper + `ban.severe`, `mute.severe`
- **admin** → mod + `admin`

Adding a new template? Pick the tier that best fits its severity and reuse the perm — don't invent a new node per template.

- Every template's `permission:` is a **hard** requirement: without it, staff cannot see the template in the `/punish` picker and cannot apply it directly.
- The template permission does NOT imply the category permission. A staff member with a template perm but not `staffcore.punish` cannot use `/punish` at all.
- If a template's `permission:` is missing or empty, it falls back to `staffcore.admin`.

## Reloading

`/staffcore reload` re-parses `punishments/punishments.yml` and rebuilds the template catalogue. Existing usage rows in the database are not affected.
