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
- `teleports/`, `refund/`, `gamemodes/`, `chat/`, `reports/`, `vanish/`,
  `freeze/`, `inspect/`, `spy/`, `staffchat/`, `announcement/`, `maintenance/`,
  `staffclear/` and `utils/` per-feature settings for the optional feature groups gated by
  `features.<name>` in `config/config.yml`. `chat/` also holds
  `blocked-words.yml`, the anti-swear filter; `reports/` holds the two GUI
  layouts for the report list and the single-report view.
- `commands/` per-group command visibility and execution filter, with
  optional replacement responses for `/pl`, `/version` and `/help`, plus
  the `/staffmode` toggle. Four files: `config.yml` (groups, blocked
  message, brand), `fakes.yml` (replacement responses + tab-complete
  plugin list), `leak-hide.yml` (extra visibility toggles),
  `staffmode.yml` (per-tier lists, messages and sound for `/staffmode`).
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
