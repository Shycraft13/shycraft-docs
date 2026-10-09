# `economy/team/config.yml`

Location: `plugins/EconomyCore/economy/team/config.yml`

```yaml
team:
  invite-expiry-seconds: 60
  home-teleport-delay: 5
  min-name-length: 3
  max-name-length: 15
  max-members: 20
  allow-color-codes: false
  allow-symbols: false
```

- `min-name-length` / `max-name-length` count only visible characters — colour codes and MiniMessage tags do not count. `&aB` is one character (`B`).
- `allow-color-codes: false` rejects any raw input containing `&<c>`, `&#RRGGBB` or `<...>` tags. Set to `true` to let team names contain colours.
- `allow-symbols: false` restricts the visible text to letters, digits and underscore. Set to `true` to allow other symbols in team names.
- Both rules apply to `/team create` and `/team rename` identically.
