# `economy/pay/gui/confirm.yml`

Location: `plugins/EconomyCore/economy/pay/gui/confirm.yml`

```yaml
PAY-CONFIRM-MENU:
  TITLE: "&8ᴄᴏɴꜰɪʀᴍ ᴘᴀʏᴍᴇɴᴛ"
  SIZE: 27

  BUTTONS:
    CANCEL:
      MATERIAL: RED_STAINED_GLASS_PANE
      TITLE: "&#FC0000&lCANCEL"
      SLOT: 11
      LORE:
        - "&7Cancel"
        - ""
        - "&#FC0000Information"
        - "&fCancel this payment"
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Cancel"

    INFO:
      MATERIAL: PLAYER_HEAD
      TITLE: "&#00FC00&l%player%"
      SLOT: 13
      LORE:
        - "&7Payment"
        - ""
        - "&#00FC00Information"
        - "&fAmount: &#00FC00%amount%"
        - "&fTo: &#00FC99%player%"

    CONFIRM:
      MATERIAL: LIME_STAINED_GLASS_PANE
      TITLE: "&#00FC00&lCONFIRM"
      SLOT: 15
      LORE:
        - "&7Confirm"
        - ""
        - "&#00FC00Information"
        - "&fPay &#00FC00%amount% &fto"
        - "&#00FC99%player%"
        - ""
        - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Confirm"
```
