# `update/confirm.yml`

Location: `plugins/StaffCore/update/confirm.yml`

Layout and text for the `/staffcore update` confirm GUI. `/staffcore update`
ships the StaffCore JAR of the `<from>` node to one or many other nodes over
Redis. Receivers stage the file in `plugins/update/<jarname>.jar`; Bukkit
atomically swaps it in on their next server restart. Missing config files
the new JAR ships get recreated by `ResourceUpdater` on that first enable.

The confirm GUI is opened as the last stage of the interactive picker
(`/staffcore update` with no arguments) AND for the scripted variant
(`/staffcore update <from> <to|*>`) so a chat typo can't ship a JAR by
accident. Skipped for the scripted variant when the caller appends
`--yes` (or `-y`) at the end of the command, and always skipped when the
sender is console.

The layout mirrors the auction confirm menu: 3 rows, `CANCEL` on the left
(slot 11, red glass pane), `SUMMARY` in the middle (slot 13, paper, all info
in its lore), `CONFIRM` on the right (slot 15, lime glass pane).

## Placeholders

Available in every `TITLE` / `LORE` string and in the `MESSAGES` block:

| Placeholder | Meaning |
| --- | --- |
| `%source%` | Server-id of the source node (the one whose JAR ships) |
| `%target-count%` | Number of receiver server-ids |
| `%target-list%` | Comma-separated server-ids (`*` resolves to the concrete list) |
| `%jar-name%` | File name of the JAR. Shows `(remote)` when the source isn't this node |
| `%jar-size-kb%` | Size in kilobytes. Shows `?` when the source isn't this node |
| `%version%` | Version of the JAR. Shows `?` when the source isn't this node |
| `%staff%` | Name of the pusher (or `console`) |

`MESSAGES.update-sent` and `MESSAGES.update-failed` additionally receive:

| Placeholder | Meaning |
| --- | --- |
| `%ok%` | Number of receivers that acknowledged |
| `%total%` | Number of receivers targeted |

## Default file

```yaml
GUI:
  ROWS: 3
  TITLE: "&8ᴄᴏɴꜰɪʀᴍ ᴜᴘᴅᴀᴛᴇ"

SUMMARY:
  MATERIAL: PAPER
  SLOT: 13
  TITLE: "&#FCE300&lᴜᴘᴅᴀᴛᴇ ѕᴜᴍᴍᴀʀʏ"
  LORE:
    - "&7Push JAR"
    - ""
    - "&#FCE300Source"
    - "&fFrom:    &#00FC99%source%"
    - ""
    - "&#FCE300Targets"
    - "&fCount:   &#00A4FC%target-count%"
    - "&fList:    &7%target-list%"
    - ""
    - "&#FCE300Payload"
    - "&fJAR:     &#00FC99%jar-name%"
    - "&fVersion: &#00A4FC%version%"
    - "&fSize:    &#00A4FC%jar-size-kb% KB"
    - "&fPusher:  &#00FC99%staff%"

CANCEL:
  MATERIAL: RED_STAINED_GLASS_PANE
  SLOT: 11
  TITLE: "&#FC0000&lCANCEL"
  LORE:
    - "&7Cancel Update"
    - ""
    - "&#FC0000Information"
    - "&fCancel and keep"
    - "&fevery node's JAR"
    - "&funtouched."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Cancel"

CONFIRM:
  MATERIAL: LIME_STAINED_GLASS_PANE
  SLOT: 15
  TITLE: "&#00FC00&lCONFIRM"
  LORE:
    - "&7Confirm Update"
    - ""
    - "&#00FC00Information"
    - "&fShip the JAR of"
    - "&f&#00FC99%source% &fto &#00A4FC%target-count% &fnode(s)."
    - "&fReceivers swap it in on"
    - "&ftheir next restart."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Confirm"

MESSAGES:
  update-sent:    "&#00FC99StaffCore update: &f%ok%/%total% &7sent &8(from=&f%source%&8, jar=&f%jar-name%&8)"
  update-failed:  "&#FC0000StaffCore update failed &8(from=&f%source%&8, jar=&f%jar-name%&8). See console for details."
  cancelled:      "&7Update cancelled."
  scripted-hint:  "&7Tip: append &f--yes&7 to skip this confirm in scripts."
```

## Sections

| Key | Purpose |
| --- | --- |
| `GUI.ROWS` | GUI height, 1..6 (clamped). Default `3` (27 slots). |
| `GUI.TITLE` | Window title. Legacy `&` colours + `&#RRGGBB` hex. |
| `CANCEL` | Left button (slot 11). Closes the GUI without pushing and sends `MESSAGES.cancelled`. |
| `SUMMARY` | Center paper item (slot 13) showing what is about to be shipped. Set `MATERIAL`, `SLOT`, `TITLE`, `LORE`. |
| `CONFIRM` | Right button (slot 15). Triggers the update. |
| `MESSAGES.update-sent` | Chat feedback on a completed update. |
| `MESSAGES.update-failed` | Chat feedback when the update receives zero acknowledgements. |
| `MESSAGES.cancelled` | Chat feedback on Cancel. |
| `MESSAGES.scripted-hint` | Tip line shown to guide operators toward `--yes` for automation. |

Slots are 0-indexed with the top-left corner at `0`. In a 3-row GUI (default)
the range is `0..26`; in a 6-row GUI it is `0..53`. Any button whose `SLOT`
falls outside the current `GUI.ROWS` is silently dropped.

## Scripting

For automated updates (cron, rcon, shell scripts) always append `--yes`:

```
/staffcore update lobby * --yes
```

`<from>` may be this node's own server-id (direct send) or any live node
(Redis request — the named source reads and publishes its own JAR). Console
callers never see the GUI even without `--yes`, so a script running from
`console.log` shell works either way, but `--yes` is recommended so intent
is explicit.

## Reload

`/staffcore reload` re-reads this file alongside every other config; new
values apply the next time the GUI opens.
