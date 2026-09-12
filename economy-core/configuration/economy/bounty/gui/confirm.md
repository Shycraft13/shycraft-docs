# `economy/bounty/gui/confirm.yml`

Location: `plugins/EconomyCore/economy/bounty/gui/confirm.yml`

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
