# `economy/homes/gui/mainmenu.yml`

Location: `plugins/EconomyCore/economy/homes/gui/mainmenu.yml`

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
