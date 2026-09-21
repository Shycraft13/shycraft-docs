# `punishments/screens.yml`

Location: `plugins/StaffCore/punishments/screens.yml`

Multi-line disconnect screens shown to banned or kicked players. Uses legacy
`&` colours and `&#RRGGBB` hex colours.

**Placeholders:** `%reason%`, `%staff%`, `%date%`, `%expires%`, `%remaining%`.

```yaml
ban:
  permanent: |-
    &#FC0000&lYOU HAVE BEEN PERMANENTLY BANNED

    &fReason: &#FCE300%reason%
    &fBanned by: &#00FC99%staff%

  temporary: |-
    &#FC0000&lYOU HAVE BEEN BANNED

    &fReason: &#FCE300%reason%
    &fBanned by: &#00FC99%staff%
    &fRemaining: &#FCE300%remaining%

kick: |-
  &#F97603&lYOU HAVE BEEN KICKED

  &fReason: &#FCE300%reason%
  &fKicked by: &#00FC99%staff%
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
