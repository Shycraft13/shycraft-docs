# Team (`economy/team/`)

Full team system with members, permissions, shared home and a PvP toggle.

## `economy/team/config.yml`

```yaml
team:
  invite-expiry-seconds: 60
  home-teleport-delay: 5
  min-name-length: 3
  max-name-length: 15
  max-members: 20
```

## `economy/team/gui/confirm.yml`

```yaml
kick-title: "&8ᴋɪᴄᴋ %player%"
disband-title: "&8ᴅɪѕʙᴀɴᴅ ᴛᴇᴀᴍ"

confirm:
  MATERIAL: LIME_STAINED_GLASS_PANE
  TITLE: "&#00FC00&lCONFIRM"
  LORE:
    - "&7Action"
    - ""
    - "&#00FC00Information"
    - "&fConfirm the action"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Confirm"

cancel:
  MATERIAL: RED_STAINED_GLASS_PANE
  TITLE: "&#FC0000&lCANCEL"
  LORE:
    - "&7Action"
    - ""
    - "&#FC0000Information"
    - "&fCancel the action"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Cancel"

kick-info:
  MATERIAL: PLAYER_HEAD
  TITLE: "&#FC0000&lKICK %player%"
  LORE:
    - "&7Kick Confirmation"
    - ""
    - "&#FC0000Information"
    - "&fAre you sure you want"
    - "&fto kick &#00FC99%player%&f?"

disband-info:
  MATERIAL: BARRIER
  TITLE: "&#FC0000&lDISBAND TEAM"
  LORE:
    - "&7Disband Confirmation"
    - ""
    - "&#FC0000Information"
    - "&fAre you sure you want"
    - "&fto disband the team?"
    - "&fThis cannot be undone."
```

## `economy/team/gui/main.yml`

```yaml
gui:
  title: "&8%team%"

sort:
  MATERIAL: HOPPER
  TITLE: "&#FCE300&lSORT"
  LORE-HEADER:
    - "&7Member Order"
    - ""
    - "&7Current Selection"
  LORE-FOOTER:
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Change"
  ACTIVE-PREFIX: "&#FCE300▶ &f"
  INACTIVE-PREFIX: "&7▶ &f"

  MODES:
    ONLINE:         "Online"
    MONEY:          "Balance"
    ALPHABETICALLY: "Alphabetically"
    JOIN_DATE:      "Join Date"

refresh:
  MATERIAL: IRON_HELMET
  TITLE: "&#00FC00&lREFRESH"
  LORE:
    - "&7Members"
    - ""
    - "&#00FC00Information"
    - "&fRefresh the member list"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Refresh"

home-set:
  MATERIAL: LIME_BANNER
  TITLE: "&#00FC00&lTEAM HOME"
  LORE:
    - "&7Team Location"
    - ""
    - "&#00FC00Information"
    - "&fTeleport to team home"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Teleport"

home-none:
  MATERIAL: WHITE_BANNER
  TITLE: "&7&lTEAM HOME"
  LORE:
    - "&7Team Location"
    - ""
    - "&7Information"
    - "&fNo team home set."
    - "&fUse /team sethome"

pvp-on:
  MATERIAL: IRON_SWORD
  TITLE: "&#00FC00&lPVP ENABLED"
  LORE:
    - "&7Team PvP"
    - ""
    - "&#00FC00Information"
    - "&fTeam PvP is &#00FC00enabled&f."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Disable"

pvp-off:
  MATERIAL: IRON_SWORD
  TITLE: "&#FC0000&lPVP DISABLED"
  LORE:
    - "&7Team PvP"
    - ""
    - "&#FC0000Information"
    - "&fTeam PvP is &#FC0000disabled&f."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Enable"

prev-page:
  MATERIAL: ARROW
  TITLE: "&#FC0000&lPREVIOUS PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fGo to the previous page"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"

next-page:
  MATERIAL: ARROW
  TITLE: "&#00FC00&lNEXT PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#00FC00Information"
    - "&fGo to the next page"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Next Page"
```

## `economy/team/gui/member_edit.yml`

```yaml
gui:
  title: "&8ᴇᴅɪᴛɪɴɢ %player%"

back:
  MATERIAL: ARROW
  TITLE: "&#FC0000&lBACK"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"

kick:
  MATERIAL: CROSSBOW
  TITLE: "&#FC0000&lKICK"
  LORE:
    - "&7Member Management"
    - ""
    - "&#FC0000Information"
    - "&fKick &#00FC99%player% &ffrom"
    - "&fthe team"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Kick"

perm-edit-home:
  MATERIAL: WHITE_BED
  TITLE: "&#00FC00&lEDIT HOME"
  LORE:
    - "&7Permission"
    - ""
    - "&#00FC00Information"
    - "&fAllows setting and"
    - "&fdeleting team home"
    - ""
    - "&#00FC00▶ &fStatus: %status%"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Toggle"

perm-kick:
  MATERIAL: IRON_AXE
  TITLE: "&#FC0000&lKICK MEMBERS"
  LORE:
    - "&7Permission"
    - ""
    - "&#FC0000Information"
    - "&fAllows kicking"
    - "&fteam members"
    - ""
    - "&#FC0000▶ &fStatus: %status%"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Toggle"

perm-manage-teammates:
  MATERIAL: SHIELD
  TITLE: "&#FCE300&lMANAGE TEAMMATES"
  LORE:
    - "&7Permission"
    - ""
    - "&#FCE300Information"
    - "&fAllows editing other"
    - "&fmembers' permissions"
    - ""
    - "&#FCE300▶ &fStatus: %status%"
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Toggle"

perm-visit-home:
  MATERIAL: LIME_BANNER
  TITLE: "&#00FC00&lVISIT HOME"
  LORE:
    - "&7Permission"
    - ""
    - "&#00FC00Information"
    - "&fAllows teleporting"
    - "&fto team home"
    - ""
    - "&#00FC00▶ &fStatus: %status%"
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Toggle"

perm-pvp:
  MATERIAL: IRON_SWORD
  TITLE: "&#FC0000&lPVP TOGGLE"
  LORE:
    - "&7Permission"
    - ""
    - "&#FC0000Information"
    - "&fAllows toggling"
    - "&fteam-wide PvP"
    - ""
    - "&#FC0000▶ &fStatus: %status%"
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Toggle"

perm-team-chat:
  MATERIAL: BELL
  TITLE: "&#00A4FC&lTEAM CHAT"
  LORE:
    - "&7Permission"
    - ""
    - "&#00A4FCInformation"
    - "&fAllows using"
    - "&fteam chat"
    - ""
    - "&#00A4FC▶ &fStatus: %status%"
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Toggle"
```

## `economy/team/messages.yml`

```yaml
messages:

  created:            "&#00A4FC&lTEAM &r&7» &fTeam &#00FC99%team% &fcreated."
  already-in-team:    "&cYou are already in a team."
  not-in-team:        "&cYou are not in a team."
  not-owner:          "&cOnly the team owner can do this."
  no-permission:      "&cYou don't have permission for this."
  name-invalid:       "&cTeam name may only contain letters, digits and underscores (3–16 chars)."
  name-taken:         "&cA team with that name already exists."

  invite-sent:        "&#00A4FC&lTEAM &r&7» &fInvite sent to &#00FC99%player%&f."
  invite-received:    "&#00A4FC&lTEAM &r&7» &#00FC99%sender% &finvited you to join &#00FC99%team%&f."
  invite-accept-text: "&#00FC00[ACCEPT]"
  invite-accept-hover: "&7Click to accept the invite"
  invite-deny-text:   "&#FC0000[DENY]"
  invite-deny-hover:  "&7Click to deny the invite"
  invite-pending:     "&cThat player already has a pending invite from your team."
  target-in-team:     "&cThat player is already in a team."
  no-invite:          "&cYou have no pending team invite."
  invite-expired:     "&cThat invite has expired."

  accepted-sender:    "&#00A4FC&lTEAM &r&7» &#00FC99%player% &fjoined the team."
  you-joined:         "&#00A4FC&lTEAM &r&7» &fYou joined &#00FC99%team%&f."
  denied-sender:      "&#00A4FC&lTEAM &r&7» &#00FC99%player% &fdenied the invite."
  you-denied:         "&#00A4FC&lTEAM &r&7» &fYou denied the invite."

  left:               "&#00A4FC&lTEAM &r&7» &#00FC99%player% &fleft the team."
  you-left:           "&#00A4FC&lTEAM &r&7» &fYou left the team."
  kicked:             "&#00A4FC&lTEAM &r&7» &#00FC99%player% &fwas kicked from the team."
  you-kicked:         "&#00A4FC&lTEAM &r&7» &fYou were kicked from the team."
  disbanded:          "&#00A4FC&lTEAM &r&7» &fThe team has been disbanded."
  cant-kick-owner:    "&cYou cannot kick the team owner."
  cant-kick-self:     "&cYou cannot kick yourself."
  not-a-member:       "&cThat player is not in your team."
  owner-must-disband: "&cYou must disband the team before leaving."

  home-set:           "&#00A4FC&lTEAM &r&7» &fTeam home set."
  home-deleted:       "&#00A4FC&lTEAM &r&7» &fTeam home deleted."
  home-not-set:       "&cThis team has no home set."
  home-already-set:   "&cTeam home already set. Delete it first with /team delhome."
  home-no-visit:      "&cYou are not allowed to visit the team home."
  home-no-edit:       "&cYou are not allowed to edit the team home."
  team-changed:       "&cYou are no longer a member of this team."

  player-not-found:   "&cPlayer not found."

  chat-format:        "&#00A4FC&lTEAM &r&7» &#00FC99%player%&7: &f%message%"
  chat-no-perm:       "&cYou don't have team chat permission."
```

## `economy/team/sounds.yml`

```yaml
sounds:
  create:   "minecraft:entity.experience_orb.pickup|1.0|1.0"
  invite:   "minecraft:entity.experience_orb.pickup|1.0|1.0"
  join:     "minecraft:entity.experience_orb.pickup|1.0|1.2"
  leave:    "minecraft:entity.villager.no|1.0|1.0"
  kick:     "minecraft:entity.villager.no|1.0|1.0"
  disband:  "minecraft:entity.villager.no|1.0|0.8"
  home-set: "minecraft:entity.experience_orb.pickup|1.0|1.0"
  open:     "minecraft:ui.button.click|1.0|1.0"
```

