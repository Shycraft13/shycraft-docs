# `punishments/messages.yml`

Location: `plugins/StaffCore/punishments/messages.yml`

All chat + action-bar messages. Legacy colours (`&`) and hex colours
(`&#RRGGBB`) are both accepted.

**Placeholders:** `%player%`, `%staff%`, `%reason%`, `%duration%`, `%expires%`,
`%remaining%`, `%count%`, `%id%`, `%date%`, plus `%requested%` / `%cap%` /
`%action%` on the `limits:` keys.

One-line messages go to chat (with their prefix) and to the action bar (without
it), errors in red, see
[Chat and action bar messages](../config/config.md#chat-and-action-bar-messages).
Multi-line output (`/history`, `/warns`, `/checkban`, `/checkmute`) and
broadcasts go to chat only.

```yaml
common:
  no-permission:         "&cNo permission."
  player-not-found:      "&cPlayer not found."
  player-must-be-online: "&cPlayer must be online."
  cannot-target-self:    "&cYou cannot target yourself."
  cannot-target-staff:   "&cYou cannot target that staff member."
  error:                 "&cAction failed. See console."

ban:
  success-perm:     "&#FC0000&lBAN &r&7» &fPermanently banned &#00FC99%player%&f. Reason: &#FCE300%reason%&f."
  success-temp:     "&#FC0000&lBAN &r&7» &fBanned &#00FC99%player% &ffor &#FCE300%duration%&f. Reason: &#FCE300%reason%&f."
  broadcast-perm:   "&#FC0000&lBAN &r&7» &#00FC99%player% &fhas been permanently banned by &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."
  broadcast-temp:   "&#FC0000&lBAN &r&7» &#00FC99%player% &fhas been banned for &#FCE300%duration% &fby &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."
  ip-applied:       "&#FC0000&lBAN &r&7» &fEvery known IP of &#00FC99%player% &fis banned too."
  already-banned:   "&cPlayer is already banned."
  no-perm-perm:     "&cNo permission for permanent bans."
  no-perm-temp:     "&cNo permission for temporary bans."
  no-perm-ip:       "&cNo permission for IP bans (--ip)."

  unban-success:    "&#00FC00&lUNBAN &r&7» &fUnbanned &#00FC99%player%&f."
  unban-success-void: "&#00FC00&lUNBAN &r&7» &fUnbanned &#00FC99%player% &7(ladder step voided)&f."
  unban-broadcast:  "&#00FC00&lUNBAN &r&7» &#00FC99%player% &fhas been unbanned by &#00FC99%staff%&f."
  unban-not-banned: "&cPlayer is not banned."

  check-perm:       "&#FC0000&lBAN &r&7» &#00FC99%player% &fis permanently banned by &#00FC99%staff%&f. Reason: &#FCE300%reason%&f. Since &7%date%&f. ID: &#FCE300#%id%"
  check-temp:       "&#FC0000&lBAN &r&7» &#00FC99%player% &fis banned for &#FCE300%duration% &fby &#00FC99%staff%&f. Reason: &#FCE300%reason%&f. Expires in &#FCE300%remaining% &7(%expires%)&f. ID: &#FCE300#%id%"
  check-lifted:     "&7&lBAN &r&7» &#00FC99%player% &7was banned by &#00FC99%staff% &7on &f%date%&7. Reason: &#FCE300%reason%&7. &fLifted by &#00FC99%lifted-by% &fon &f%lifted-at%&7. ID: &#FCE300#%id%"
  check-expired:    "&7&lBAN &r&7» &#00FC99%player% &7was banned by &#00FC99%staff% &7on &f%date%&7. Reason: &#FCE300%reason%&7. &fExpired &f%expires%&7. ID: &#FCE300#%id%"

mute:
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

  unmute-success:   "&#00FC00&lUNMUTE &r&7» &fUnmuted &#00FC99%player%&f."
  unmute-broadcast: "&#00FC00&lUNMUTE &r&7» &#00FC99%player% &fhas been unmuted by &#00FC99%staff%&f."
  target-unmute:    "&#00FC00&lUNMUTE &r&7» &fYou have been unmuted."
  unmute-not-muted: "&cPlayer is not muted."

  check-perm:       "&#F97603&lMUTE &r&7» &#00FC99%player% &fis permanently muted by &#00FC99%staff%&f. Reason: &#FCE300%reason%&f. Since &7%date%&f."
  check-temp:       "&#F97603&lMUTE &r&7» &#00FC99%player% &fis muted for &#FCE300%duration% &fby &#00FC99%staff%&f. Reason: &#FCE300%reason%&f. Expires in &#FCE300%remaining% &7(%expires%)&f."

  target-chat-blocked-perm: "&#F97603&lMUTE &r&7» &fYou are permanently muted."
  target-chat-blocked-temp: "&#F97603&lMUTE &r&7» &fYou are muted for &#FCE300%remaining%&f."
  target-command-blocked:   "&#F97603&lMUTE &r&7» &fYou cannot use that command while muted."
  target-sign-blocked:      "&#F97603&lMUTE &r&7» &fYou cannot write on signs while muted."
  target-book-blocked:      "&#F97603&lMUTE &r&7» &fYou cannot write in books while muted."
  target-anvil-blocked:     "&#F97603&lMUTE &r&7» &fYou cannot rename items while muted."

warn:
  success:          "&#FCE300&lWARN &r&7» &fWarned &#00FC99%player%&f. Reason: &#FCE300%reason%&f. &7(warn #&f%count%&7)"
  broadcast:        "&#FCE300&lWARN &r&7» &#00FC99%player% &fhas been warned by &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."
  target-notify:    "&#FCE300&lWARN &r&7» &fYou have been warned. Reason: &#FCE300%reason%&f."

  unwarn-success:     "&#00FC00&lUNWARN &r&7» &fRemoved warn &7#&f%id% &ffrom &#00FC99%player%&f."
  unwarn-success-void: "&#00FC00&lUNWARN &r&7» &fVoided warn &7#&f%id% &ffrom &#00FC99%player% &7(ladder step voided)&f."
  unwarn-not-found: "&cWarn not found."

  warns-empty:      "&#FCE300&lWARNS &r&7» &fNo warns on record for &#00FC99%player%&f."
  warns-header:     "&#FCE300&lWARNS &r&7» &#00FC99%player% &7has &f%count% &7warn(s):"
  warns-entry:      "&7#&f%id% &8• &fReason: &#FCE300%reason% &8• &fBy: &#00FC99%staff% &8• &7%date%"

  check-none:       "&cNo active warns."
  check-header:     "&#FCE300&lWARNS &r&7» &#00FC99%player% &fhas &#FCE300%count% &factive warn(s), most recent:"
  check-entry:      "&7#&f%id% &8• &fReason: &#FCE300%reason% &8• &fBy: &#00FC99%staff% &8• &7%date%"

template:
  applied:      "&#00A4FC&lTEMPLATE &r&7» &fApplied &#FCE300%template% &f(tier &#FCE300%tier%&f) to &#00FC99%player%&f."
  broadcast:    "&#00A4FC&lTEMPLATE &r&7» &#00FC99%player% &freceived &#FCE300%template% &f(tier &#FCE300%tier%&f) from &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."
  wrong-category: "&c%template% is not a %category% template."
  no-permission:  "&cNo permission for template %template%."

kick:
  success:    "&#F97603&lKICK &r&7» &fKicked &#00FC99%player%&f. Reason: &#FCE300%reason%&f."
  broadcast:  "&#F97603&lKICK &r&7» &#00FC99%player% &fhas been kicked by &#00FC99%staff%&f. Reason: &#FCE300%reason%&f."

limits:
  duration-clamped: "&#F97603&lLIMIT &r&7» &fRequested &#FCE300%requested% &fexceeds your cap. Clamped to &#FCE300%cap%&f."
  duration-blocked: "&cDuration %requested% exceeds your cap of %cap%."
  require-template: "&cYou must use a template."
  cooldown-staff:   "&cCooldown on %action%. Try again in %remaining%."
  cooldown-target:  "&cThis target was just punished. Try again in %remaining%."
  cooldown-redo:    "&cYou just lifted a punishment on this target. Try again in %remaining%."
  lookup-failed:    "&cCooldowns could not be checked. Try again in a moment."

staffcore:
  reload-start:  "&#00A4FC&lRELOAD &r&7» &fReloading configuration..."
  reload-done:   "&#00FC00&lRELOAD &r&7» &fReloaded &#FCE300%files% &ffile(s) and &#FCE300%templates% &ftemplate(s) in &#FCE300%ms%ms&f."
  reload-sent:          "&#00A4FC&lRELOAD &r&7» &fReload sent to &#FCE300%target%&f."
  reload-remote-done:   "&#00FC00&lRELOAD &r&7» &#FCE300%server% &freloaded in &#FCE300%ms%ms&f."
  reload-remote-failed: "&cReload on %server% failed: %error%"
  reload-failed: "&cReload failed: %error%"
  reload-no-redis: "&cReloading another server requires Redis."
  reload-unknown-server: "&cUnknown server. Live: %servers%"
```
