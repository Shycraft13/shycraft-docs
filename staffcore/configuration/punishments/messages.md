# `punishments/messages.yml`

Location: `plugins/StaffCore/punishments/messages.yml`

All chat + action-bar messages. Legacy colours (`&`) and hex colours
(`&#RRGGBB`) are both accepted.

**Placeholders:** `%player%`, `%staff%`, `%reason%`, `%duration%`, `%expires%`,
`%remaining%`, `%count%`, `%id%`, `%date%`, plus `%requested%` / `%cap%` /
`%action%` on the `limits:` keys.

Chat is used for usage help, staff success confirmations, broadcasts, and
persistent target-notify messages. Action bar is used for brief errors
("no permission", "not found") and blocked-action feedback ("cannot chat
while muted").

```yaml
common:
  no-permission:         "&cNo permission."
  player-not-found:      "&cPlayer not found."
  player-must-be-online: "&cPlayer must be online."
  cannot-target-self:    "&cYou cannot target yourself."
  cannot-target-staff:   "&cYou cannot target that staff member."
  error:                 "&cAction failed - see console for details."

ban:
  usage:            "&#F97603Usage: &#FCE300/ban <player> [time] [reason] [--kill] [--ip]"
  success-perm:     "&#FC0000&lBAN &r&7» &fPermanently banned &#00FC99%player%&f. Reason: &#FCE300%reason%&f."
  success-temp:     "&#FC0000&lBAN &r&7» &fBanned &#00FC99%player% &ffor &#FCE300%duration%&f. Reason: &#FCE300%reason%&f."
  broadcast-perm:   "&#FC0000&lBAN &r&7» &#00FC99%player% &fhas been permanently banned by &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."
  broadcast-temp:   "&#FC0000&lBAN &r&7» &#00FC99%player% &fhas been banned for &#FCE300%duration% &fby &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."
  ip-applied:       "&#FC0000&lBAN &r&7» &fEvery known IP of &#00FC99%player% &fis banned too."
  already-banned:   "&cPlayer is already banned."
  no-perm-perm:     "&cNo permission for permanent bans."
  no-perm-temp:     "&cNo permission for temporary bans."
  no-perm-ip:       "&cNo permission for IP bans (--ip)."

  unban-usage:      "&#F97603Usage: &#FCE300/unban <player> [--void]"
  unban-success:    "&#00FC00&lUNBAN &r&7» &fUnbanned &#00FC99%player%&f."
  unban-success-void: "&#00FC00&lUNBAN &r&7» &fUnbanned &#00FC99%player% &7(ladder step voided)&f."
  unban-broadcast:  "&#00FC00&lUNBAN &r&7» &#00FC99%player% &fhas been unbanned by &#00FC99%staff%&f."
  unban-not-banned: "&cPlayer is not banned."

  check-usage:      "&#F97603Usage: &#FCE300/checkban <player|#id>"
  check-perm:       "&#FC0000&lBAN &r&7» &#00FC99%player% &fis permanently banned by &#00FC99%staff%&f. Reason: &#FCE300%reason%&f. Since &7%date%&f. ID: &#FCE300#%id%"
  check-temp:       "&#FC0000&lBAN &r&7» &#00FC99%player% &fis banned for &#FCE300%duration% &fby &#00FC99%staff%&f. Reason: &#FCE300%reason%&f. Expires in &#FCE300%remaining% &7(%expires%)&f. ID: &#FCE300#%id%"
  check-lifted:     "&7&lBAN &r&7» &#00FC99%player% &7was banned by &#00FC99%staff% &7on &f%date%&7. Reason: &#FCE300%reason%&7. &fLifted by &#00FC99%lifted-by% &fon &f%lifted-at%&7. ID: &#FCE300#%id%"
  check-expired:    "&7&lBAN &r&7» &#00FC99%player% &7was banned by &#00FC99%staff% &7on &f%date%&7. Reason: &#FCE300%reason%&7. &fExpired &f%expires%&7. ID: &#FCE300#%id%"

mute:
  usage:            "&#F97603Usage: &#FCE300/mute <player> [time] [reason] [--ip]"
  success-perm:     "&#F97603&lMUTE &r&7» &fPermanently muted &#00FC99%player%&f. Reason: &#FCE300%reason%&f."
  success-temp:     "&#F97603&lMUTE &r&7» &fMuted &#00FC99%player% &ffor &#FCE300%duration%&f. Reason: &#FCE300%reason%&f."
  broadcast-perm:   "&#F97603&lMUTE &r&7» &#00FC99%player% &fhas been permanently muted by &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."
  broadcast-temp:   "&#F97603&lMUTE &r&7» &#00FC99%player% &fhas been muted for &#FCE300%duration% &fby &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."
  ip-applied:       "&#F97603&lMUTE &r&7» &fEvery known IP of &#00FC99%player% &fis muted too."
  target-notify-perm: "&#F97603&lMUTE &r&7» &fYou have been permanently muted. Reason: &#FCE300%reason%&f."
  target-notify-temp: "&#F97603&lMUTE &r&7» &fYou have been muted for &#FCE300%duration%&f. Reason: &#FCE300%reason%&f."
  already-muted:    "&cPlayer is already muted."
  no-perm-perm:     "&cNo permission for permanent mutes."
  no-perm-temp:     "&cNo permission for temporary mutes."
  no-perm-ip:       "&cNo permission for IP mutes (--ip)."

  unmute-usage:     "&#F97603Usage: &#FCE300/unmute <player>"
  unmute-success:   "&#00FC00&lUNMUTE &r&7» &fUnmuted &#00FC99%player%&f."
  unmute-broadcast: "&#00FC00&lUNMUTE &r&7» &#00FC99%player% &fhas been unmuted by &#00FC99%staff%&f."
  target-unmute:    "&#00FC00&lUNMUTE &r&7» &fYou have been unmuted."
  unmute-not-muted: "&cPlayer is not muted."

  check-usage:      "&#F97603Usage: &#FCE300/checkmute <player>"
  check-perm:       "&#F97603&lMUTE &r&7» &#00FC99%player% &fis permanently muted by &#00FC99%staff%&f. Reason: &#FCE300%reason%&f. Since &7%date%&f."
  check-temp:       "&#F97603&lMUTE &r&7» &#00FC99%player% &fis muted for &#FCE300%duration% &fby &#00FC99%staff%&f. Reason: &#FCE300%reason%&f. Expires in &#FCE300%remaining% &7(%expires%)&f."

  target-chat-blocked-perm: "&7You are permanently muted."
  target-chat-blocked-temp: "&7You are muted for &#FCE300%remaining%&7."
  target-command-blocked:   "&7You cannot use that command while muted."
  target-sign-blocked:      "&7You cannot write on signs while muted."
  target-book-blocked:      "&7You cannot write in books while muted."
  target-anvil-blocked:     "&7You cannot rename items while muted."

warn:
  usage:            "&#F97603Usage: &#FCE300/warn <player> [reason]"
  success:          "&#FCE300&lWARN &r&7» &fWarned &#00FC99%player%&f. Reason: &#FCE300%reason%&f. &7(warn #&f%count%&7)"
  broadcast:        "&#FCE300&lWARN &r&7» &#00FC99%player% &fhas been warned by &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."
  target-notify:    "&#FCE300&lWARN &r&7» &fYou have been warned. Reason: &#FCE300%reason%&f."

  unwarn-usage:       "&#F97603Usage: &#FCE300/unwarn <player> <id> [--void]"
  unwarn-success:     "&#00FC00&lUNWARN &r&7» &fRemoved warn &7#&f%id% &ffrom &#00FC99%player%&f."
  unwarn-success-void: "&#00FC00&lUNWARN &r&7» &fVoided warn &7#&f%id% &ffrom &#00FC99%player% &7(ladder step voided)&f."
  unwarn-not-found: "&cWarn not found."

  warns-usage:      "&#F97603Usage: &#FCE300/warns <player>"
  warns-empty:      "&7No warns on record for &#00FC99%player%&7."
  warns-header:     "&#FCE300&lWARNS &r&7» &#00FC99%player% &7has &f%count% &7warn(s):"
  warns-entry:      "&7#&f%id% &8• &fReason: &#FCE300%reason% &8• &fBy: &#00FC99%staff% &8• &7%date%"

  check-usage:      "&#F97603Usage: &#FCE300/checkwarn <player>"
  check-none:       "&cNo active warns."
  check-header:     "&#FCE300&lWARNS &r&7» &#00FC99%player% &fhas &#FCE300%count% &factive warn(s), most recent:"
  check-entry:      "&7#&f%id% &8• &fReason: &#FCE300%reason% &8• &fBy: &#00FC99%staff% &8• &7%date%"

history:
  usage: "&#F97603Usage: &#FCE300/history <player>"

alts:
  usage: "&#F97603Usage: &#FCE300/alts <player>"

template:
  punish-usage: "&#F97603Usage: &#FCE300/punish <player> [template] [--kill] [--ip]"
  applied:      "&#00A4FC&lTEMPLATE &r&7» &fApplied &#FCE300%template% &f(tier &#FCE300%tier%&f) to &#00FC99%player%&f."
  broadcast:    "&#00A4FC&lTEMPLATE &r&7» &#00FC99%player% &freceived &#FCE300%template% &f(tier &#FCE300%tier%&f) from &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."
  wrong-category: "&c&#FCE300%template% &cis not a %category% template."
  no-permission:  "&cNo permission for template &#FCE300%template%&c."

kick:
  usage:      "&#F97603Usage: &#FCE300/kick <player> [reason]"
  success:    "&#F97603&lKICK &r&7» &fKicked &#00FC99%player%&f. Reason: &#FCE300%reason%&f."
  broadcast:  "&#F97603&lKICK &r&7» &#00FC99%player% &fhas been kicked by &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."

limits:
  duration-clamped: "&#F97603&lLIMIT &r&7» &fRequested &#FCE300%requested% &fexceeds your cap. Clamped to &#FCE300%cap%&f."
  duration-blocked: "&cDuration &f%requested% &cexceeds your cap of &f%cap%&c."
  require-template: "&cYou must use a template. Try &f/punish <player> <template>&c."
  cooldown-staff:   "&cCooldown on &f%action%&c. Try again in &f%remaining%&c."
  cooldown-target:  "&cThis target was just punished. Try again in &f%remaining%&c."
  cooldown-redo:    "&cYou just lifted a punishment on this target. Try again in &f%remaining%&c."

staffcore:
  usage:         "&#F97603Usage: &#FCE300/staffcore reload"
  reload-start:  "&#00A4FC&lRELOAD &r&7» &fReloading configuration..."
  reload-done:   "&#00FC00&lRELOAD &r&7» &fReloaded &#FCE300%files% &ffile(s) and &#FCE300%templates% &ftemplate(s) in &#FCE300%ms%ms&f."
  reload-failed: "&cReload failed: %error%"
```
