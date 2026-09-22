# `push/confirm.yml`

Location: `plugins/StaffCore/push/confirm.yml`

Layout and text for the `/staffcore push` confirm GUI. Opened as the last
stage of the interactive picker (`/staffcore push` with no arguments) AND for
the scripted variant (`/staffcore push <from> <to|*> <preset>`) so a chat
typo can't push by accident. Skipped for the scripted variant when the caller
appends `--yes` (or `-y`) at the end of the command, and always skipped when
the sender is console.

The layout mirrors the auction confirm menu: 3 rows, `CANCEL` on the left
(slot 11, red glass pane), `SUMMARY` in the middle (slot 13, paper, all info
in its lore), `CONFIRM` on the right (slot 15, lime glass pane).

## Placeholders

Available in every `TITLE` / `LORE` string and in the `MESSAGES` block:

| Placeholder | Meaning |
| --- | --- |
| `%source%` | Server-id of the source node (the one whose configs will be published) |
| `%target-count%` | Number of receiver server-ids |
| `%target-list%` | Comma-separated server-ids (`*` resolves to the concrete list) |
| `%preset%` | Preset name, lower-case (`punishments`, `database`, `gui`, `all`) |
| `%preset-upper%` | Preset name, upper-case |
| `%file-count%` | Number of files in the preset bundle. Shows `?` if the source isn't this node (only the source knows its own file count until it publishes) |
| `%staff%` | Name of the pusher (or `console`) |

`MESSAGES.push-sent` and `MESSAGES.push-failed` additionally receive:

| Placeholder | Meaning |
| --- | --- |
| `%ok%` | Number of receivers that acknowledged |
| `%total%` | Number of receivers targeted |

## Default file

```yaml
GUI:
  ROWS: 3
  TITLE: "&8ᴄᴏɴꜰɪʀᴍ ᴘᴜѕʜ"

SUMMARY:
  MATERIAL: PAPER
  SLOT: 13
  TITLE: "&#FCE300&lᴘᴜѕʜ ѕᴜᴍᴍᴀʀʏ"
  LORE:
    - "&7Push Configs"
    - ""
    - "&#FCE300Source"
    - "&fFrom:   &#00FC99%source%"
    - ""
    - "&#FCE300Targets"
    - "&fCount:  &#00A4FC%target-count%"
    - "&fList:   &7%target-list%"
    - ""
    - "&#FCE300Bundle"
    - "&fPreset: &#00FC99%preset-upper%"
    - "&fFiles:  &#00A4FC%file-count%"
    - "&fPusher: &#00FC99%staff%"

CANCEL:
  MATERIAL: RED_STAINED_GLASS_PANE
  SLOT: 11
  TITLE: "&#FC0000&lCANCEL"
  LORE:
    - "&7Cancel Push"
    - ""
    - "&#FC0000Information"
    - "&fCancel and keep"
    - "&fevery node's configs"
    - "&funtouched."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Cancel"

CONFIRM:
  MATERIAL: LIME_STAINED_GLASS_PANE
  SLOT: 15
  TITLE: "&#00FC00&lCONFIRM"
  LORE:
    - "&7Confirm Push"
    - ""
    - "&#00FC00Information"
    - "&fShip &#00A4FC%file-count% &ffile(s) from"
    - "&f&#00FC99%source% &fto &#00A4FC%target-count% &fnode(s)."
    - "&fReceivers auto-reload."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Confirm"

MESSAGES:
  push-sent:     "&#00FC99StaffCore push: &f%ok%/%total% &7sent &8(from=&f%source%&8, preset=&f%preset-upper%&8)"
  push-failed:   "&#FC0000StaffCore push failed &8(from=&f%source%&8, preset=&f%preset-upper%&8). See console for details."
  cancelled:     "&7Push cancelled."
  scripted-hint: "&7Tip: append &f--yes&7 to skip this confirm in scripts."
```

## Sections

| Key | Purpose |
| --- | --- |
| `GUI.ROWS` | GUI height, 1..6 (clamped). Default `3` (27 slots). |
| `GUI.TITLE` | Window title. Legacy `&` colours + `&#RRGGBB` hex. |
| `CANCEL` | Left button (slot 11). Closes the GUI without pushing and sends `MESSAGES.cancelled`. |
| `SUMMARY` | Center paper item (slot 13) showing what is about to happen. Set `MATERIAL`, `SLOT`, `TITLE`, `LORE`. |
| `CONFIRM` | Right button (slot 15). Triggers the push. |
| `MESSAGES.push-sent` | Chat feedback on a completed push. |
| `MESSAGES.push-failed` | Chat feedback when the push receives zero acknowledgements. |
| `MESSAGES.cancelled` | Chat feedback on Cancel. |
| `MESSAGES.scripted-hint` | Tip line shown to guide operators toward `--yes` for automation. |

Slots are 0-indexed with the top-left corner at `0`. In a 3-row GUI (default)
the range is `0..26`; in a 6-row GUI it is `0..53`. Any button whose `SLOT`
falls outside the current `GUI.ROWS` is silently dropped.

## Scripting

For automated pushes (cron, rcon, shell scripts) always append `--yes`:

```
/staffcore push lobby * punishments --yes
```

`<from>` may be this node's own server-id (direct send) or any live node
(Redis request — the named source reads and publishes its own configs).
Console callers never see the GUI even without `--yes`, so a script running
from `console.log` shell works either way, but `--yes` is recommended so
intent is explicit.

## Reload

`/staffcore reload` re-reads this file alongside every other config; new
values apply the next time the GUI opens.
