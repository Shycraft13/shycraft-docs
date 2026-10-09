# `commands/leak-hide.yml`

Location: `plugins/StaffCore/commands/leak-hide.yml`

Extra visibility toggles that sit outside the per-group whitelist in
[`config.yml`](config.md).

## hide-plugin-channels

When `true`, the plugin-channel announcement (`minecraft:register` and
`minecraft:unregister`) is not sent to clients. Plugin messaging still
works. Skipped for players with `staffcore.admin` or
`staffcore.commands.bypass`.

Set to `false` if a specific mod on your player base complains it
cannot see a channel it needs.

## extra-hidden-roots

An additive list of command roots to strip from the tab-complete graph
on top of the built-in list. Each entry is a single root name, no
leading `/`. Use this when a third-party plugin adds a command whose
name you do not want visible for any group.

Do not list commands here that are legitimate player-facing features
(auction, kits, order, ...). Those still need to be in per-group
`tab-complete` lists in [`config.yml`](config.md).

## File shape

```yaml
hide-plugin-channels: true

extra-hidden-roots: []
```
