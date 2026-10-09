# `commands/staffmode.yml`

Location: `plugins/StaffCore/commands/staffmode.yml`

Configures the `/staffmode` toggle: messages, feedback sound, and the
optional on-screen indicator. The per-group command visibility itself
lives in [`config.yml`](config.md); this file just controls what the
toggle *feels* like.

## What staffmode does

Every staff member normally looks like a plain player: their
tab-complete only shows the commands the `default` group lists, so a
moderator hitting TAB in chat sees the same list as any player. When
they run `/staffmode`, their group's `staff-commands` list flips into
the tab. `/staffmode` again returns them to the default view.

Execution is separate from visibility. A staffer's `staff-commands`
can always be typed and will always run, even with staffmode off —
the toggle only decides whether TAB shows them or not. That way a
moderator can quickly type `/mute name` from chat without giving up
their "looks like a normal player" appearance.

## Command

`/staffmode` toggles the sender's own staffmode. No sub-commands, no
player targeting, no tab completions — the command is a single verb.

State is per-session — a server restart or rejoin drops it and the
staffer is back to the base view until they run `/staffmode` again
(unless `persist: true` is enabled).

## `enabled`

Master switch. `false` disables `/staffmode` entirely.

## `indicator`

On-screen reminder shown while staffmode is on:

- `actionbar` — refreshed every `indicator-refresh-seconds`
- `bossbar` — persistent bar at the top
- `none` — no indicator (default; the tab-change is signal enough)

## `indicator-refresh-seconds`

How often the actionbar / bossbar indicator text refreshes. An actionbar
message fades after about 3 seconds, so 2 keeps it visible without
refreshing more often than needed. Clamped to 1..30.

## `persist`

If `true`, staffmode state is persisted so a staffer who was ON
before a restart or relog comes back ON. Default `false` (in-memory
only). Note: currently in-memory only in v1 — the flag is present but
persistence isn't yet wired.

## `messages`

Every string is optional. Empty string = silent (nothing shown).

Only the following keys are read by the current pure-toggle code
path. Any other keys in the yaml are ignored.

- `toggled-on` — action-bar shown to the toggling player on ON.
  Convention: `&7` gray, action-bar is a status channel not a chat
  notification.
- `toggled-off` — action-bar on OFF.
- `no-permission` — action-bar + villager.no when the player lacks
  `staffcore.staffmode`.
- `not-staff` — action-bar + villager.no when the player's group is
  not a staff group (`staff: true` missing).
- `console-self` — sent when the server console tries to run
  `/staffmode` (which has no target).
- `indicator` — the text shown by the actionbar / bossbar indicator
  loop while staffmode is on.
- `revoked-auto` — shown when staffmode is auto-disabled because the
  player's group lost its `staff: true` flag (config reload or perm
  change while online).

## `sound`

Feedback sound played to the player on toggle. Format:
`namespace:key|volume|pitch`. Empty string = silent.

- `enter` — plays on toggle-ON.
- `exit` — plays on toggle-OFF.

Note: the keys are `enter` / `exit`, NOT `on` / `off`. Both `on` and
`off` are reserved boolean keys in YAML 1.1, which SnakeYAML uses;
using them here would break the config reader silently. Legacy
installs that still have `on` / `off` on disk are read as a fallback.

Error feedback always plays `entity.villager.no` and is not
configurable here — that is the shared error cue used across the
plugin.

## Example

```yaml
enabled: true

indicator: none

indicator-refresh-seconds: 2

persist: false

messages:
  toggled-on:            "&7Staffmode enabled."
  toggled-off:           "&7Staffmode disabled."

  no-permission:         "&cNo permission."
  not-staff:             "&cYour group is not a staff group."
  console-self:          "&cConsole cannot toggle its own staffmode."

  indicator:             "&#F97603Staffmode active"

  revoked-auto:          "&cStaffmode disabled - group no longer eligible."

sound:
  enter: "minecraft:block.note_block.pling|1.0|1.4"
  exit:  "minecraft:block.note_block.pling|1.0|0.8"
```
