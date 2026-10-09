# `staffchat/config.yml`

Location: `plugins/StaffCore/staffchat/config.yml`

`/staffchat` toggles the sender into the staff channel: while it is on, every
message they write in chat is kept out of public chat and sent to staff instead.
Everyone holding `staffcore.staffchat` sees it, on any server.

Placeholders in `FORMAT`: `%player%` (sender), `%message%` (what they typed) and
`%server%` (the server id of the sending server).

```yaml
staffchat:
  cross-server: true

FORMAT: "&#FF5555&lSTAFFCHAT &r&#FF5555%player% &r&7» &f%message%"

TOGGLE-ON:  "&#FF5555&lSTAFFCHAT &r&7» &fYou are now writing in the staff channel. Run /staffchat again to leave."
TOGGLE-OFF: "&#FF5555&lSTAFFCHAT &r&7» &fYou returned to public chat."
```
