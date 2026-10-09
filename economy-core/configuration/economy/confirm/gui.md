# `economy/confirm/gui.yml`

Location: `plugins/EconomyCore/economy/confirm/gui.yml`

The one confirm menu every admin command that targets `*` (all online players)
opens before it runs. `/moneymanager`, `/shardmanager`, `/bountymanager`,
`/kitmanager`, `/tagsmanager` and `/combatmanager` all share this menu, so a `*`
action looks the same everywhere.

Placeholders in `TITLE` and in every `LORE` line: `%command%` (the exact command
waiting for confirmation) and `%count%` (how many players are online right now
and would be hit).

`ENABLED: false` runs a `*` command straight away with no menu. The console never
gets the menu either and always runs straight away.

```yaml
CONFIRM-MENU:
  ENABLED: true
  TITLE: "&8ᴄᴏɴꜰɪʀᴍ"
  SIZE: 27

  BUTTONS:
    CANCEL:
      MATERIAL: RED_STAINED_GLASS_PANE
      TITLE: "&#FC0000&lCANCEL"
      SLOT: 11
      LORE:
        - "&7Action"
        - ""
        - "&#FC0000Information"
        - "&fRun nothing and"
        - "&fclose this menu"
        - ""
        - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Cancel"

    INFO:
      MATERIAL: PAPER
      TITLE: "&#FCE300&lSUMMARY"
      SLOT: 13
      LORE:
        - "&7Preview"
        - ""
        - "&#FCE300Information"
        - "&f%command%"
        - "&fAffects &#FCE300%count% &fonline players"

    CONFIRM:
      MATERIAL: LIME_STAINED_GLASS_PANE
      TITLE: "&#00FC00&lCONFIRM"
      SLOT: 15
      LORE:
        - "&7Action"
        - ""
        - "&#00FC00Information"
        - "&fRun it for all"
        - "&#00FC00%count% &fonline players"
        - ""
        - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Confirm"
```
