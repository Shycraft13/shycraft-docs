# Configuration

This section reproduces every YAML file shipped with staffcore, laid out in the
exact folder structure they have under `plugins/StaffCore/`.

Each page shows one file so you can diff your local copy against the shipped
default after an update. Comments are stripped: the pages show only the actual
key/value structure you need to edit.

Top-level roots:

- `config/` global settings: master `config.yml`, database credentials + Redis,
  and the permission-node registry.
- `punishments/` everything related to bans, mutes, warns, kicks and templates:
  behaviour toggles, chat messages, disconnect screens, sounds, the template
  catalogue, and the three GUI layouts.
- `teleports/`, `refund/`, `gamemodes/`, `chat/` per-feature settings for the
  optional feature groups gated by `features.<name>` in `config/config.yml`.
- `push/`, `update/` GUI layouts for the `/staffcore push` and
  `/staffcore update` confirm screens.

Use `/staffcore reload` to reload every file at runtime. Note: some flags
(mute chat interception, DB backend selection) are only read at startup and
need a server restart to take effect.

## Auto-merge

Every shipped resource is merged on plugin enable: keys added in a newer
release are appended to your existing file with the shipped default, but values
you already customised are never overwritten. Delete a file entirely to
regenerate it from scratch on next start.
