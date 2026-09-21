# Punishment Templates

Templates are pre-defined punishments with a tier ladder. Instead of typing `/ban Steve 3d Cheating` for a first offence and `/ban Steve 30d Cheating` for a fourth, you configure the whole progression once and let staff apply `/punish Steve cheating` for every offence. The plugin picks the right tier automatically.

The template model is closely modelled on LiteBans. If you have a LiteBans `templates.yml` sitting around, moving it over is mostly a placeholder-rename job (see [Placeholders](#placeholders) below).

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

Placeholders use `%name%` everywhere, **not** `$name`. If you're porting LiteBans templates, replace every `$name` with `%name%`.

## Shipped defaults

The plugin ships with eight example templates covering the most common offences. See [`punishments/punishments.yml`](configuration/punishments/punishments.md) for the full text. Delete the whole file (and any of its templates) to start from scratch; the file regenerates on next start if it's missing.

## Permissions and templates

- Every template's `permission:` is a **hard** requirement: without it, staff cannot see the template in the `/punish` picker and cannot apply it directly.
- The template permission does NOT imply the category permission. A staff member with `staffcore.template.cheating` but not `staffcore.punish` cannot use `/punish` at all.
- If a template's `permission:` is missing or empty, it falls back to `staffcore.admin`.

## Reloading

`/staffcore reload` re-parses `punishments/punishments.yml` and rebuilds the template catalogue. Existing usage rows in the database are not affected.
