# Homes (`economy/homes/`)

Per-player named homes with a full management GUI.

## `economy/homes/config.yml`

```yaml
homes:
  max: 10
  default: 2
  teleport-delay: 5
```

## `economy/homes/gui/delete.yml`

```yaml
DELETE-MENU:
  TITLE: "&8ᴅᴇʟᴇᴛᴇ ʜᴏᴍᴇ %number%"
  SIZE: 27

  BUTTONS:
    CANCEL:
      MATERIAL: RED_STAINED_GLASS_PANE
      TITLE: "&#FC0000&lCANCEL"
      SLOT: 10
      LORE:
        - "&7Keep Home"
        - ""
        - "&#FC0000Information"
        - "&fKeep Home %number%"
        - "&fand close this menu"
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Cancel"

    CONFIRM:
      MATERIAL: LIME_STAINED_GLASS_PANE
      TITLE: "&#00FC00&lCONFIRM"
      SLOT: 16
      LORE:
        - "&7Delete Home"
        - ""
        - "&#00FC00Information"
        - "&fPermanently delete"
        - "&fHome %number%"
        - ""
        - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Confirm"

    HOME:
      MATERIAL: LIME_BED
      TITLE: "&#00FC00&lHOME %number%"
      SLOT: 13
      LORE:
        - "&7Home Preview"
        - ""
        - "&#00FC00Information"
        - "&fAre you sure you want to"
        - "&fdelete Home %number%?"
```

## `economy/homes/gui/mainmenu.yml`

```yaml
HOMES-MENU:
  TITLE: "&8ʏᴏᴜʀ ʜᴏᴍᴇꜱ"
  SIZE: 54

  SLOTS:
    "1":
      BED: 11
      DYE: 20
    "2":
      BED: 12
      DYE: 21
    "3":
      BED: 13
      DYE: 22
    "4":
      BED: 14
      DYE: 23
    "5":
      BED: 15
      DYE: 24
    "6":
      BED: 29
      DYE: 38
    "7":
      BED: 30
      DYE: 39
    "8":
      BED: 31
      DYE: 40
    "9":
      BED: 32
      DYE: 41
    "10":
      BED: 33
      DYE: 42

  BED:
    NO-HOME:
      MATERIAL: LIGHT_GRAY_BED
      TITLE: "&#AAAAAA&lEMPTY SLOT"
      LORE:
        - "&7No Home Set"
        - ""
        - "&7Information"
        - "&fThis slot is empty."
        - "&fClick to set Home %number%"
        - ""
        - "&7▶ &7&l&nCLICK&r &7to Set Home"

    HAS-HOME:
      MATERIAL: LIME_BED
      TITLE: "&#00FC00&lHOME %number%"
      LORE:
        - "&7Home"
        - ""
        - "&#00FC00Information"
        - "&fClick to teleport to your home"
        - ""
        - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Teleport"

    NO-PERMISSION:
      MATERIAL: RED_BED
      TITLE: "&#FC0000&lLIMIT REACHED"
      LORE:
        - "&7Locked Slot"
        - ""
        - "&#FC0000Information"
        - "&fYou reached your home limit."
        - "&fDelete a home to free a slot"

  DYE:
    NO-HOME:
      MATERIAL: LIGHT_GRAY_DYE
      TITLE: "&#AAAAAA&lEMPTY SLOT"
      LORE:
        - "&7Empty Slot"
        - ""
        - "&7Information"
        - "&fNo home set here."
        - "&fClick to set Home %number%"
        - ""
        - "&7▶ &7&l&nCLICK&r &7to Set Home"

    HAS-HOME:
      MATERIAL: LIME_DYE
      TITLE: "&#FC0000&lDELETE HOME"
      LORE:
        - "&7Delete Home"
        - ""
        - "&#FC0000Information"
        - "&fClick to delete"
        - "&fHome %number%"
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Delete"

    NO-PERMISSION:
      MATERIAL: RED_DYE
      TITLE: "&#FC0000&lLIMIT REACHED"
      LORE:
        - "&7Locked Slot"
        - ""
        - "&#FC0000Information"
        - "&fYou reached your home limit."
        - "&fDelete a home to free a slot"
```

## `economy/homes/messages.yml`

```yaml
messages:
  home-set:         "&#00A4FC&lHOME &r&7» &fHome &#FCE300%name% &fset."
  home-deleted:     "&#00A4FC&lHOME &r&7» &fHome &#FCE300%name% &fdeleted."
  home-not-found:   "&cNo home found."
  home-teleported:  "&7Arrived at &#FCE300%name%&7."
  home-teleporting: "&7Teleporting to &#FCE300%name%&7 in &#FCE300%delay%s&7..."
  max-homes:        "&cYou reached the home limit."
  no-homes:         "&cYou have no homes set."
  cooldown:         "&7Please wait &#FCE300%time%s&7."
  no-permission:    "&cNo permission for that slot."
  homes-full:       "&cAll home slots are full."
```

## `economy/homes/sounds.yml`

```yaml
sounds:
  click: "minecraft:ui.button.click|1.0|1.0"
  home-set: "minecraft:entity.player.levelup|1.0|1.0"
  home-teleported: "minecraft:entity.experience_orb.pickup|1.0|1.0"
  home-deleted: "minecraft:entity.item.break|1.0|1.0"
```

