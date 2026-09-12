# Bounty (`economy/bounty/`)

Bounty placement menu, confirmation and player-facing messages.

## `economy/bounty/gui/confirm.yml`

```yaml
CONFIRM-MENU:
  TITLE: "&8ᴄᴏɴꜰɪʀᴍ ʙᴏᴜɴᴛʏ"
  SIZE: 27

  BUTTONS:
    CANCEL:
      SLOT: 11
      MATERIAL: RED_STAINED_GLASS_PANE
      TITLE: "&#FC0000&lCANCEL"
      LORE:
        - "&7Bounty Confirmation"
        - ""
        - "&#FC0000Information"
        - "&fCancel and return"
        - "&fto the bounty list."
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Cancel"

    TARGET:
      SLOT: 13
      TITLE: "&#FC0000%name%"
      LORE:
        - "&7Bounty Target"
        - ""
        - "&#FC0000Information"
        - "&#00FC00&l$ &fAmount: &#00FC00%amount%"

    CONFIRM:
      SLOT: 15
      MATERIAL: LIME_STAINED_GLASS_PANE
      TITLE: "&#00FC00&lCONFIRM"
      LORE:
        - "&7Bounty Confirmation"
        - ""
        - "&#00FC00Information"
        - "&fPlace &#00FC00%amount% &fbounty"
        - "&fon &#FC0000%name%&f."
        - ""
        - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Confirm"
```

## `economy/bounty/gui/mainmenu.yml`

```yaml
gui:
  title: "&8ʙᴏᴜɴᴛɪᴇѕ"

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
  MATERIAL: SKELETON_SKULL
  TITLE: "&#FC0000&lREFRESH"
  LORE:
    - "&7Bounty List"
    - ""
    - "&#FC0000Information"
    - "&fRefresh the"
    - "&fbounty list."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Refresh"

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
  TITLE: "&#FC0000#%position% %name%"
  LORE:
    - "&7Bounty: &#00FC00%amount%"

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

## `economy/bounty/messages.yml`

```yaml
messages:
  placed: "&#FC0000&lBOUNTY &r&7» &fPlaced &#00FC00%amount% &fbounty on &#FC0000%player%&f."
  received: "&#FC0000&lBOUNTY &r&7» &fA bounty of &#00FC00%amount% &fhas been placed on you."
  claimed: "&#FC0000&lBOUNTY &r&7» &fYou claimed &#00FC00%amount% &fbounty from &#FC0000%player%&f."
  not-enough-money: "&7Not enough money."
  cannot-self: "&cYou cannot put a bounty on yourself."
  player-not-found: "&cPlayer not found."
  invalid-amount: "&cInvalid amount."
  cooldown: "&7Please wait before adding another bounty."
  usage: "&cUsage: /bounty [add <player> <amount>]"
```

## `economy/bounty/sounds.yml`

```yaml
sounds:
  open: "minecraft:block.chest.open|1.0|1.0"
  add: "minecraft:entity.player.levelup|1.0|1.5"
  claim: "minecraft:entity.player.levelup|1.0|2.0"
  no-money: "minecraft:entity.villager.no|1.0|1.0"
```

