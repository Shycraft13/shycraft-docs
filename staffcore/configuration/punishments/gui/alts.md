# `punishments/gui/alts.yml`

Location: `plugins/StaffCore/punishments/gui/alts.yml`

Layout of the `/alts <player>` viewer GUI. 4 rows / 36 slots. Slots 0..26
hold alt entries (player heads). Slots 27..35 are the navigation row.

IPs themselves are never rendered here (only counted). Query the database
directly if you need the raw addresses.

**Title / lore placeholders:** `%player%`, `%uuid%`, `%total%`, `%page%`,
`%maxpage%`.
**Alt item extras:** `%name%`, `%uuid%`, `%status%`, `%status-color%`,
`%shared-ips%`, `%last-seen%`.

```yaml
GUI:
  TITLE: "&8%player%'s ᴀʟᴛѕ"

LOADING:
  MATERIAL: CLOCK
  SLOT: 31
  TITLE: "&#FCE300Loading alts..."
  LORE:
    - "&7Fetching accounts"

PREV-PAGE:
  MATERIAL: ARROW
  SLOT: 27
  TITLE: "&#00A4FC&lPREV PAGE"
  LORE:
    - "&7Page &f%page% &7/ &f%maxpage%"

TARGET-HEAD:
  SLOT: 31
  TITLE: "&#FCE300&l%player%"
  LORE:
    - "&7Target Player"
    - ""
    - "&#FCE300Information"
    - "&fTotal alts: &#00A4FC%total%"
    - "&fPage: &7%page% &7/ &f%maxpage%"

NEXT-PAGE:
  MATERIAL: ARROW
  SLOT: 35
  TITLE: "&#00A4FC&lNEXT PAGE"
  LORE:
    - "&7Page &f%page% &7/ &f%maxpage%"

ALT-ITEM:
  COLOR-ONLINE:  "&#00FC99"
  COLOR-OFFLINE: "&7"
  COLOR-BANNED:  "&#FC0000"

  LABEL-ONLINE:  "Online"
  LABEL-OFFLINE: "Offline"
  LABEL-BANNED:  "Banned"

  TITLE: "%status-color%&l%name%"
  LORE:
    - ""
    - "&fStatus: %status-color%%status%"
    - "&fShared IPs: &#FCE300%shared-ips%"
    - "&fLast seen: &7%last-seen%"
    - ""

EMPTY:
  MATERIAL: BARRIER
  SLOT: 13
  TITLE: "&#FC0000No alts found"
  LORE:
    - "&7This player has never shared"
    - "&7an IP with another account."
```

## Section reference

| Section | Purpose |
| --- | --- |
| `GUI.TITLE` | Window title. |
| `LOADING` | Placeholder rendered while the alt query is in-flight. |
| `PREV-PAGE` / `NEXT-PAGE` | Pagination arrows. |
| `TARGET-HEAD` | Player-head slot for the target. Material is always `PLAYER_HEAD`. |
| `ALT-ITEM` | Rendered per alt account. `COLOR-*` and `LABEL-*` are the per-status overrides applied via `%status-color%` and `%status%`. |
| `EMPTY` | Shown when the target has never shared an IP with any other account. |

## Sort order

Alts are sorted online → banned → offline, with ties broken by the most
recent last-seen timestamp.

## Head textures

Head textures resolve to the alt's real skin, including for offline-only
accounts. The first render for a never-seen UUID may take a moment while
the profile is fetched; subsequent renders are instant.
