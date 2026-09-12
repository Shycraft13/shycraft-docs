# Pay (`economy/pay/`)

/pay command, optional confirmation menu, sounds and messages.

## `economy/pay/config.yml`

```yaml
pay:
  min-amount: 1.0
  max-amount: 100000000000000.0

  cooldown-seconds: 1

  spam-max-payments: 5
  spam-window-seconds: 30
  spam-block-seconds: 60
```

## `economy/pay/gui/confirm.yml`

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

## `economy/pay/messages.yml`

```yaml
messages:
  success-sender:     "&#00FC00&lPAY &r&7» &fPaid &#00FC00%amount% &fto &#00FC99%player%&f."
  success-receiver:   "&#00FC00&lPAY &r&7» &fReceived &#00FC00%amount% &ffrom &#00FC99%player%&f."
  insufficient-funds: "&cNot enough money."
  invalid-amount:     "&cInvalid amount."
  self-pay:           "&cYou cannot pay yourself."
  player-not-found:   "&cPlayer not found."
  cooldown:           "&7Please wait before paying again."
  spam-blocked:       "&cToo many payments. Try again in &#FCE300%time%&c."
```

## `economy/pay/sounds.yml`

```yaml
sounds:
  success: "minecraft:entity.experience_orb.pickup|1.0|1.0"
```

