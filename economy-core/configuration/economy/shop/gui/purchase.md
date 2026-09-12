# `economy/shop/gui/purchase.yml`

Location: `plugins/EconomyCore/economy/shop/gui/purchase.yml`

```yaml
PURCHASE-SHOP-MENU:
  TITLE: "&8ᴘᴜʀᴄʜᴀꜱᴇ"
  SIZE: 27

  BUTTONS:
    CANCEL:
      MATERIAL: RED_STAINED_GLASS_PANE
      TITLE: "&#FC0000&lCANCEL"
      SLOT: 21
      LORE:
        - "&7Go Back"
        - ""
        - "&#FC0000Information"
        - "&fReturn to shop"
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Cancel"

    CONFIRM:
      MATERIAL: LIME_STAINED_GLASS_PANE
      TITLE: "&#00FC00&lCONFIRM"
      SLOT: 23
      LORE:
        - "&7Purchase"
        - ""
        - "&#00FC00Information"
        - "&7Quantity: &f%quantity%"
        - "&7Total: &#00FC00%price%"
        - ""
        - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Confirm"

    DISPLAY:
      SLOT: 13

      TITLE: "%item%"
      LORE:
        - " "
        - "&7Quantity: &f%quantity%"
        - "&7Total: &#00FC00%price%"

    MINUS_64:
      MATERIAL: RED_STAINED_GLASS_PANE
      TITLE: "&#FC0000&l-64"
      SLOT: 9
      LORE:
        - "&7Decrease by 64"

    MINUS_10:
      MATERIAL: RED_STAINED_GLASS_PANE
      TITLE: "&#FC0000&l-10"
      SLOT: 10
      LORE:
        - "&7Decrease by 10"

    MINUS_1:
      MATERIAL: RED_STAINED_GLASS_PANE
      TITLE: "&#FC0000&l-1"
      SLOT: 11
      LORE:
        - "&7Decrease by 1"

    PLUS_1:
      MATERIAL: LIME_STAINED_GLASS_PANE
      TITLE: "&#00FC00&l+1"
      SLOT: 15
      LORE:
        - "&7Increase by 1"

    PLUS_10:
      MATERIAL: LIME_STAINED_GLASS_PANE
      TITLE: "&#00FC00&l+10"
      SLOT: 16
      LORE:
        - "&7Increase by 10"

    PLUS_64:
      MATERIAL: LIME_STAINED_GLASS_PANE
      TITLE: "&#00FC00&l+64"
      SLOT: 17
      LORE:
        - "&7Increase by 64"
```
