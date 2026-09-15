# `economy/team/messages.yml`

Location: `plugins/EconomyCore/economy/team/messages.yml`

```yaml
messages:

  created:            "&#00A4FC&lTEAM &r&7» &fTeam &#00FC99%team% &fcreated."
  already-in-team:    "&cYou are already in a team."
  not-in-team:        "&cYou are not in a team."
  not-owner:          "&cOnly the team owner can do this."
  no-permission:      "&cYou don't have permission for this."
  name-invalid:       "&cTeam name may only contain letters, digits and underscores (3-16 chars)."
  name-taken:         "&cA team with that name already exists."

  invite-sent:        "&#00A4FC&lTEAM &r&7» &fInvite sent to &#00FC99%player%&f."
  # %accept% and %deny% inline the clickable buttons defined below.
  invite-received:    "&#00A4FC&lTEAM &r&7» &#00FC99%sender% &finvited you to join &#00FC99%team%&f. %accept% %deny%"
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

  # ── /teammanager admin command ───────────────────────────────────────────
  teammanager-usage:               "&cUsage: /teammanager <forcedisband|view|teamhome> <player_or_team>"
  teammanager-usage-forcedisband:  "&cUsage: /teammanager forcedisband <player_or_team>"
  teammanager-usage-view:          "&cUsage: /teammanager view <player_or_team>"
  teammanager-usage-teamhome:      "&cUsage: /teammanager teamhome <player_or_team>"
  teammanager-only-players-view:   "&cOnly players can open the team view."
  teammanager-only-players-home:   "&cOnly players can be teleported to a team home."
  # Placeholders: %team%
  teammanager-forcedisband:        "&#00A4FC&lADMIN &r&7» &fForce disbanded team &#00FC99%team%&f."
  teammanager-no-home:             "&cTeam &#00FC99%team%&c has no home set."
  # Placeholders: %input%
  teammanager-not-found:           "&cNo team or player found matching &f%input%&c."
```
