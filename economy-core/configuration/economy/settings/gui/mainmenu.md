# `economy/settings/gui/mainmenu.yml`

Location: `plugins/EconomyCore/economy/settings/gui/mainmenu.yml`

```yaml
TITLE: "&8ѕᴇᴛᴛɪɴɢѕ"
SIZE: 45

STATUS:
  ENABLED: "&#00FC00Enabled"
  DISABLED: "&#FC0000Disabled"
  TEAM_ONLY: "&#00A4FCTeam only"

global-chat:
  SLOT: 10
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
  MATERIAL: FILLED_MAP
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
```
