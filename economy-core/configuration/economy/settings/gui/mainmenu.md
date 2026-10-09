# `economy/settings/gui/mainmenu.yml`

Location: `plugins/EconomyCore/economy/settings/gui/mainmenu.yml`

This file is the whole `/settings` menu. A setting is shown only when it has a
section here with a `SLOT`, so removing a section removes the entry and a setting
that your file does not list yet simply has no row in the menu (it still works and
keeps its default). After adding or editing a section, run `/economy reload`.

`DEFAULT: true/false` per section is the value a player starts with who has never
touched that setting. Changing it affects only players who have nothing stored yet;
everyone who has already played keeps the state they set. Leave the key out to use
the plugin's own default. Tri-state settings (`global-chat`, `private-messages`,
`tpa-requests`, `tpahere-requests`, `payments`) start at enabled or disabled;
"Team only" is reachable by clicking. `tpa-auto` is session-only and is never
stored, so its `DEFAULT` applies on every rejoin.

`SIZE` is optional and only raises the menu size; the menu is always at least big
enough for the highest `SLOT` you use.

```yaml
TITLE: "&8ѕᴇᴛᴛɪɴɢѕ"
SIZE: 45

STATUS:
  ENABLED: "&#00FC00Enabled"
  DISABLED: "&#FC0000Disabled"
  TEAM_ONLY: "&#00A4FCTeam only"

global-chat:
  SLOT: 10
  DEFAULT: true
  MATERIAL: PAPER
  TITLE: "&#00A4FC&lGLOBAL CHAT"
  LORE:
    - "&7Chat"
    - ""
    - "&#00A4FCInformation"
    - "&fSee chat messages"
    - "&ffrom other players"
    - "&f(Team only: only your team)"
    - ""
    - "&#00A4FC▶ &fStatus: %status%"
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Toggle"

private-messages:
  SLOT: 11
  DEFAULT: true
  MATERIAL: WRITABLE_BOOK
  TITLE: "&#A303F9&lPRIVATE MESSAGES"
  LORE:
    - "&7Chat"
    - ""
    - "&#A303F9Information"
    - "&fReceive private"
    - "&fmessages from players"
    - ""
    - "&#A303F9▶ &fStatus: %status%"
    - ""
    - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to Toggle"

team-chat:
  SLOT: 12
  DEFAULT: false
  MATERIAL: BELL
  TITLE: "&#00A4FC&lTEAM CHAT"
  LORE:
    - "&7Chat"
    - ""
    - "&#00A4FCInformation"
    - "&fRoute your messages"
    - "&fto team chat"
    - ""
    - "&#00A4FC▶ &fStatus: %status%"
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Toggle"

hotbar-messages:
  SLOT: 13
  DEFAULT: true
  MATERIAL: NAME_TAG
  TITLE: "&#AAAAAA&lHOTBAR MESSAGES"
  LORE:
    - "&7Display"
    - ""
    - "&#AAAAAAInformation"
    - "&fShow server messages"
    - "&fin your action bar"
    - ""
    - "&#AAAAAA▶ &fStatus: %status%"
    - ""
    - "&#AAAAAA▶ &#AAAAAA&l&nCLICK&r &#AAAAAAto Toggle"

sound-notifications:
  SLOT: 14
  DEFAULT: true
  MATERIAL: NOTE_BLOCK
  TITLE: "&#A303F9&lSOUND NOTIFICATIONS"
  LORE:
    - "&7Sound"
    - ""
    - "&#A303F9Information"
    - "&fHear plugin notification"
    - "&fsounds in-game"
    - ""
    - "&#A303F9▶ &fStatus: %status%"
    - ""
    - "&#A303F9▶ &#A303F9&l&nCLICK&r &#A303F9to Toggle"

ping-notifications:
  SLOT: 17
  DEFAULT: true
  MATERIAL: BELL
  TITLE: "&#FCE300&lPING NOTIFICATIONS"
  LORE:
    - "&7Chat"
    - ""
    - "&#FCE300Information"
    - "&fHear a sound when"
    - "&fsomeone @-mentions you"
    - ""
    - "&#FCE300▶ &fStatus: %status%"
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Toggle"

bounty-alerts:
  SLOT: 15
  DEFAULT: true
  MATERIAL: SKELETON_SKULL
  TITLE: "&#FC0000&lBOUNTY ALERTS"
  LORE:
    - "&7Bounty"
    - ""
    - "&#FC0000Information"
    - "&fReceive a message when"
    - "&fyou claim a bounty"
    - ""
    - "&#FC0000▶ &fStatus: %status%"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Toggle"

scoreboard:
  SLOT: 16
  DEFAULT: true
  MATERIAL: LECTERN
  TITLE: "&#FCE300&lSCOREBOARD"
  LORE:
    - "&7Display"
    - ""
    - "&#FCE300Information"
    - "&fShow or hide the"
    - "&fscoreboard sidebar"
    - ""
    - "&#FCE300▶ &fStatus: %status%"
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Toggle"

worth-lore:
  SLOT: 28
  DEFAULT: false
  MATERIAL: BOOK
  TITLE: "&#00FC00&lWORTH LORE"
  LORE:
    - "&7Display"
    - ""
    - "&#00FC00Information"
    - "&fShow item worth in"
    - "&fyour inventory lore"
    - ""
    - "&#00FC00▶ &fStatus: %status%"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Toggle"

tpa-requests:
  SLOT: 19
  DEFAULT: true
  MATERIAL: ENDER_PEARL
  TITLE: "&#FCE300&lTPA REQUESTS"
  LORE:
    - "&7Teleport"
    - ""
    - "&#FCE300Information"
    - "&fAllow others to send"
    - "&fyou /tpa requests"
    - ""
    - "&#FCE300▶ &fStatus: %status%"
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Toggle"

tpahere-requests:
  SLOT: 20
  DEFAULT: true
  MATERIAL: ENDER_EYE
  TITLE: "&#FC0000&lTPAHERE REQUESTS"
  LORE:
    - "&7Teleport"
    - ""
    - "&#FC0000Information"
    - "&fAllow others to send"
    - "&fyou /tpahere requests"
    - ""
    - "&#FC0000▶ &fStatus: %status%"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Toggle"

tpa-confirm-menu:
  SLOT: 21
  DEFAULT: true
  MATERIAL: COMPASS
  TITLE: "&#AAAAAA&lTPA CONFIRM MENU"
  LORE:
    - "&7Teleport"
    - ""
    - "&#AAAAAAInformation"
    - "&fShow confirm GUI"
    - "&fbefore sending /tpa"
    - ""
    - "&#AAAAAA▶ &fStatus: %status%"
    - ""
    - "&#AAAAAA▶ &#AAAAAA&l&nCLICK&r &#AAAAAAto Toggle"

payments:
  SLOT: 22
  DEFAULT: true
  MATERIAL: GOLD_INGOT
  TITLE: "&#FCE300&lPAYMENTS"
  LORE:
    - "&7Economy"
    - ""
    - "&#FCE300Information"
    - "&fAllow others to"
    - "&fpay you money"
    - ""
    - "&#FCE300▶ &fStatus: %status%"
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Toggle"

pay-confirm-menu:
  SLOT: 23
  DEFAULT: false
  MATERIAL: EMERALD
  TITLE: "&#00FC00&lPAY CONFIRM MENU"
  LORE:
    - "&7Economy"
    - ""
    - "&#00FC00Information"
    - "&fShow confirm GUI"
    - "&fbefore paying someone"
    - ""
    - "&#00FC00▶ &fStatus: %status%"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Toggle"

team-invites:
  SLOT: 24
  DEFAULT: true
  MATERIAL: SHIELD
  TITLE: "&#00FC00&lTEAM INVITES"
  LORE:
    - "&7Team"
    - ""
    - "&#00FC00Information"
    - "&fAllow others to"
    - "&finvite you to a team"
    - ""
    - "&#00FC00▶ &fStatus: %status%"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Toggle"

random-coords:
  SLOT: 25
  DEFAULT: false
  MATERIAL: RECOVERY_COMPASS
  TITLE: "&#FCE300&lRANDOM COORDS"
  LORE:
    - "&7Privacy"
    - ""
    - "&#FCE300Information"
    - "&fShow fake coordinates"
    - "&fin your F3 overlay"
    - ""
    - "&#FCE300▶ &fStatus: %status%"
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Toggle"

tpa-auto:
  SLOT: 26
  DEFAULT: false
  MATERIAL: CHORUS_FRUIT
  TITLE: "&#00A4FC&lTPA AUTO ACCEPT"
  LORE:
    - "&7Teleport"
    - ""
    - "&#00A4FCInformation"
    - "&fAutomatically accept all"
    - "&fincoming teleport requests"
    - ""
    - "&8Resets on relog, death or restart"
    - ""
    - "&#00A4FC▶ &fStatus: %status%"
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Toggle"

rtpqueue:
  SLOT: 32
  DEFAULT: true
  MATERIAL: COMPASS
  TITLE: "&#00A4FC&lRTP QUEUE"
  LORE:
    - "&7Teleport"
    - ""
    - "&#00A4FCInformation"
    - "&fReceive broadcasts when"
    - "&fplayers join the 1v1 queue"
    - ""
    - "&#00A4FC▶ &fStatus: %status%"
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Toggle"

totem-particles:
  SLOT: 29
  DEFAULT: true
  MATERIAL: TOTEM_OF_UNDYING
  TITLE: "&#00FC00&lTOTEM PARTICLES"
  LORE:
    - "&7Visual"
    - ""
    - "&#00FC00Information"
    - "&fSee totem of undying"
    - "&fanimations nearby"
    - ""
    - "&#00FC00▶ &fStatus: %status%"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Toggle"

explosion-particles:
  SLOT: 30
  DEFAULT: true
  MATERIAL: TNT
  TITLE: "&#FC0000&lEXPLOSION PARTICLES"
  LORE:
    - "&7Visual"
    - ""
    - "&#FC0000Information"
    - "&fSee explosion visual"
    - "&feffects in the world"
    - ""
    - "&#FC0000▶ &fStatus: %status%"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Toggle"

explosion-sounds:
  SLOT: 31
  DEFAULT: true
  MATERIAL: TNT_MINECART
  TITLE: "&#FC0000&lEXPLOSION SOUNDS"
  LORE:
    - "&7Sound"
    - ""
    - "&#FC0000Information"
    - "&fHear explosion sounds"
    - "&fin the world"
    - ""
    - "&#FC0000▶ &fStatus: %status%"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Toggle"

phantom-spawns:
  SLOT: 33
  DEFAULT: true
  MATERIAL: PHANTOM_MEMBRANE
  TITLE: "&#AAAAAA&lPHANTOM SPAWNS"
  LORE:
    - "&7Spawns"
    - ""
    - "&#AAAAAAInformation"
    - "&fAllow phantoms to"
    - "&fspawn near you"
    - ""
    - "&#AAAAAA▶ &fStatus: %status%"
    - ""
    - "&#AAAAAA▶ &#AAAAAA&l&nCLICK&r &#AAAAAAto Toggle"

mob-spawns:
  SLOT: 34
  DEFAULT: true
  MATERIAL: ZOMBIE_HEAD
  TITLE: "&#FC0000&lMOB SPAWNS"
  LORE:
    - "&7Spawns"
    - ""
    - "&#FC0000Information"
    - "&fAllow hostile mobs"
    - "&fto spawn near you"
    - ""
    - "&#FC0000▶ &fStatus: %status%"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Toggle"

sell-shulker-boxes:
  SLOT: 39
  DEFAULT: true
  MATERIAL: SHULKER_BOX
  TITLE: "&#00FC00&lSELL SHULKER BOXES"
  LORE:
    - "&7Economy"
    - ""
    - "&#00FC00Information"
    - "&fSell the shulker box"
    - "&fitself along with its"
    - "&fcontents, in /sell and"
    - "&fwith the sell axe"
    - ""
    - "&8Contents always sell"
    - ""
    - "&#00FC00▶ &fStatus: %status%"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Toggle"

auction-notifications:
  SLOT: 40
  DEFAULT: true
  MATERIAL: GOLD_INGOT
  TITLE: "&#00A4FC&lAUCTION NOTIFICATIONS"
  LORE:
    - "&7Notifications"
    - ""
    - "&#00A4FCInformation"
    - "&fSee auction house"
    - "&fannouncements in chat"
    - ""
    - "&#00A4FC▶ &fStatus: %status%"
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Toggle"

order-notifications:
  SLOT: 41
  DEFAULT: true
  MATERIAL: BOOK
  TITLE: "&#00A4FC&lORDER NOTIFICATIONS"
  LORE:
    - "&7Notifications"
    - ""
    - "&#00A4FCInformation"
    - "&fSee order"
    - "&fannouncements in chat"
    - ""
    - "&#00A4FC▶ &fStatus: %status%"
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Toggle"
```
