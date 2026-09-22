# `refund/gui/view.yml`

Location: `plugins/StaffCore/refund/gui/view.yml`

Hands-on view of a snapshot. Opened by clicking **View** in the
[action menu](action.md). Behaves like a real chest that never persists
changes: you interact with the items exactly the way you'd interact with
a chest's contents in vanilla.

## Click model

| Gesture | Behaviour |
| --- | --- |
| Left click | Pick up the whole stack / place from cursor / swap. |
| Right click | Pick up half (rounded up) / place one from cursor. |
| Shift left or right | Auto-transfer the stack into your own inventory. Anything that doesn't fit stays in the view slot. |
| Drop (Q) | Drop one from the hovered slot. |
| Ctrl + drop | Drop the whole hovered stack. |
| Drag (hold + drag) | Distributes the held cursor across your own inventory slots the standard vanilla way. Drag inside the view itself is not supported: use single clicks there. |

Anything on your cursor when you close the GUI is returned to your
inventory, so nothing is lost on Esc or disconnect. The snapshot on disk
is never modified: close and reopen to restore every item.

Close returns to the action menu.

Requires `staffcore.refund.giveout` to interact; without it every click
shows a permission error.

## Slot layout

**Inventory snapshots** — 45 slots (5 rows), matches `/invsee`:

| Slots | Contents |
| --- | --- |
| 0..8 | Hotbar (inventory slots 0..8) |
| 9..35 | Main storage (inventory slots 9..35) |
| 36..39 | Armor mirrored (helmet, chestplate, leggings, boots) |
| 40 | Offhand |
| 41..44 | Padding (empty, usable as scratch within the session) |

**Enderchest snapshots** — dynamic size (27, 36, 45, or 54 slots):

The view is as tall as the target's vanilla enderchest was at capture
time. A vanilla 3-row enderchest renders 27 slots; a Canvas 6-row
enderchest renders 54. Rows are computed as `ceil(size / 9)` clamped to
1..6. Slots map 1:1 to enderchest slots.

## Config

```yaml
GUI:
  TITLE: "&8%category% ᴠɪᴇᴡ"
```

Placeholders in `TITLE`: `%player%`, `%category%`.

## Sections

| Section | Purpose |
| --- | --- |
| `GUI.TITLE` | Window title. Row count and slot layout are fixed in code. |

Small-caps font (paste characters directly, don't type them):
`ᴀʙᴄᴅᴇꜰɢʜɪᴊᴋʟᴍɴᴏᴘǫʀѕᴛᴜᴠᴡxʏᴢ`
