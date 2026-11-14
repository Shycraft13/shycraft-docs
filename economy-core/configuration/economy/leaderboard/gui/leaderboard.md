# `economy/leaderboard/gui/leaderboard.yml`

Location: `plugins/EconomyCore/economy/leaderboard/gui/leaderboard.yml`

```yaml
gui:
  title: "&8ʟᴇᴀᴅᴇʀʙᴏᴀʀᴅ %type%"

prev-page:
  SLOT: 45
  MATERIAL: ARROW
  TITLE: "&#FC0000&lPREVIOUS PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fGo to the"
    - "&fprevious page"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to go back"

search:
  SLOT: 48
  MATERIAL: OAK_SIGN
  TITLE: "&#00A4FC&lSEARCH"
  LORE:
    - "&7Player Search"
    - ""
    - "&#00A4FCInformation"
    - "&fSearch for a player"
    - "&fby name."
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Search"

search-active:
  SLOT: 48
  MATERIAL: OAK_SIGN
  TITLE: "&#00FC99&lSEARCH"
  LORE:
    - "&7Player Search"
    - ""
    - "&#00FC99Information"
    - "&fFiltering: &#00FC99%query%&f."
    - "&fType empty to clear."
    - ""
    - "&#00FC99▶ &#00FC99&l&nCLICK&r &#00FC99to Search Again"

refresh:
  SLOT: 49
  COOLDOWN-MS: 3000
  MATERIAL: PLAYER_HEAD
  TITLE: "%color%&lREFRESH"
  LORE:
    - "&7Your Position"
    - ""
    - "%color%Information"
    - "&fPosition: %color%%position%"
    - "&f%type%: %color%%value%"
    - ""
    - "%color%▶ %color%&l&nCLICK&r %color%to Refresh"

sort:
  SLOT: 50
  MATERIAL: HOPPER
  TITLE: "&#FCE300&lSORT"
  LORE-HEADER:
    - "&7Listing Order"
    - ""
    - "&7Current Selection"
  LORE-FOOTER:
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Change"
  ACTIVE-PREFIX: "&#FCE300▶ &f"
  INACTIVE-PREFIX: "&7▶ &f"
  MODES:
    HIGHEST:        "Highest"
    LOWEST:         "Lowest"
    ALPHABETICALLY: "Alphabetically"

entry:
  TITLE: "%color%#%position% %name%"
  LORE:
    - "&7%type%: %color%%value%"

next-page:
  SLOT: 53
  MATERIAL: ARROW
  TITLE: "&#00FC00&lNEXT PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#00FC00Information"
    - "&fGo to the"
    - "&fnext page"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to go forward"
```

## Placeholders

The window title and the `prev-page`, `next-page`, `search`, `search-active` and `refresh` items
accept PlaceholderAPI placeholders, resolved against the player looking at the menu. The full list
of EconomyCore placeholders is on the [placeholder page](../../../../placeholders.md); any
installed expansion works too (`%luckperms_prefix%`, `%vault_eco_balance%`, ...). Without
PlaceholderAPI the text stays as typed.

`entry` and `sort` do not. An `entry` row describes the listed player, not the viewer, so a
placeholder there would show the wrong person's numbers. Use the row's own keys instead:

| Key | In | Shows |
| --- | --- | --- |
| `%position%` | `entry`, `refresh` | Rank number |
| `%name%` | `entry` | Listed player's name |
| `%value%` | `entry`, `refresh` | That player's value, formatted |
| `%type%` | `entry`, `refresh`, `gui.title` | Category name, for example `Balance` |
| `%color%` | `entry`, `refresh` | The category colour from `category.yml` |
| `%query%` | `search-active` | The name currently being filtered for |

For a live top list in a menu item, put the placeholders on the category buttons instead, see
[`category.yml`](category.md).
