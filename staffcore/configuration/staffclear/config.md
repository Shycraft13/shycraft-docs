# `staffclear/config.yml`

Location: `plugins/StaffCore/staffclear/config.yml`

`/staffclear <player>` resets everything a player can only have as staff, as
if they had never been staff: staff mode, vanish, staff chat toggle, spy
targets, maintenance bypass, fly, fly and walk speed, gamemode (back to
survival) and an open `/invsee` or `/echestsee` edit window. Punishment
history and alt records stay. Works for players online on any backend and for
offline players (applied on their next join).

```yaml
staffclear:
  cross-server: true

  auto-clear:
    enabled: true
    check-interval-seconds: 5

  messages:
    usage:          "&cUsage: /staffclear <player>"
    cleared:        "&aReset all staff state of &f%player%&a."
    cleared-target: "&7Your staff state was reset."
```

## Options

| Key | Default | Purpose |
| --- | --- | --- |
| `cross-server` | `true` | Per-feature switch on top of the network-wide `cross-server.enabled`. Both must be on for a clear to reach a player who is online on another server right now. When off, the stored state is still cleared, but a player online elsewhere keeps fly and gamemode until they switch servers. |
| `auto-clear.enabled` | `true` | Reset players automatically once they lose `staffcore.staff`. Only players who held `staffcore.staff` before are ever reset, so grant it to every staff role in your permission plugin. |
| `auto-clear.check-interval-seconds` | `5` | How often each online player is checked. The permission must be missing on two checks in a row before the reset runs. |

Independent of `auto-clear`: a player in staff mode whose group lost
`staff: true`, or who lost `staffcore.staffmode`, drops out of staff mode.

## Messages

Placeholder: `%player%`. `cleared-target` is shown to the reset player if
they are online; leave it empty for no message.
