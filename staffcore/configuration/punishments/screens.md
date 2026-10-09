# `punishments/screens.yml`

Location: `plugins/StaffCore/punishments/screens.yml`

Multi-line disconnect screens shown to banned or kicked players. Uses legacy
`&` colours and `&#RRGGBB` hex colours.

**Placeholders:** `%reason%`, `%staff%`, `%date%`, `%expires%`, `%remaining%`.

```yaml
ban:
  permanent: |-
    &cYou have been permanently banned for %reason%

    &7Banned on: &f%date%
    &7Ban ID: &f#%id%

    &7You may appeal this ban on &#00A4FCdiscord.gg/yourserver

  temporary: |-
    &cYou have been temporarily banned for %reason%

    &7Banned on: &f%date%
    &7Ban ID: &f#%id%
    &7Expires in: &f%remaining%

    &7You may appeal this ban on &#00A4FCdiscord.gg/yourserver

kick: |-
  &cYou have been kicked for %reason%

  &7Kicked on: &f%date%
  &7Kicked by: &f%staff%

  &7You may appeal this kick on &#00A4FCdiscord.gg/yourserver
```

## Which template is used

| Screen | Used when |
| --- | --- |
| `ban.permanent` | Any permanent ban (`/ban <player> <reason>` without a time argument, or a template with `duration: permanent`). |
| `ban.temporary` | Any temporary ban with a duration. `%remaining%` renders the time until expiry. |
| `kick` | Every `/kick` and every kick-category template. |

## Per-template screen overrides

Individual template ladder steps can override the screen with their own
`message:` field, useful for escalating warnings. See
[`punishments.yml`](punishments.md) for the syntax.

## Proxy edition

Same file on the proxy at `plugins/staffcoreproxy/punishments/screens.yml`.
Used when the proxy performs the disconnect on the edge.
