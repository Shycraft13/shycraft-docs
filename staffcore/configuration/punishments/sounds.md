# `punishments/sounds.yml`

Location: `plugins/StaffCore/punishments/sounds.yml`

Sounds played on specific events. Format is `"namespace:key|volume|pitch"`.
Set any value to an empty string or delete the key to disable that sound.

```yaml
common:
  error: "minecraft:entity.villager.no|0.6|0.9"

gui:
  click: "minecraft:ui.button.click|0.5|1.0"

ban:
  staff-issued: "minecraft:entity.wither.death|0.6|1.0"
  staff-unban:  "minecraft:entity.player.levelup|0.6|1.0"

mute:
  staff-issued:   "minecraft:entity.villager.no|0.6|1.0"
  staff-unmute:   "minecraft:entity.player.levelup|0.6|1.0"
  target-blocked: "minecraft:entity.villager.no|0.4|0.8"

warn:
  staff-issued:  "minecraft:block.note_block.pling|0.6|0.7"
  staff-unwarn:  "minecraft:block.note_block.pling|0.6|1.2"
  target-notify: "minecraft:entity.experience_orb.pickup|0.6|0.6"

kick:
  staff-issued: "minecraft:entity.villager.no|0.8|1.0"

refund:
  take:     "minecraft:entity.item.pickup|0.6|1.2"
  replace:  "minecraft:entity.experience_orb.pickup|0.6|1.0"
  giveout:  "minecraft:entity.shulker.close|0.6|1.2"
  teleport: "minecraft:entity.enderman.teleport|0.5|1.0"
```

## Sound keys

| Key | Played when |
| --- | --- |
| `common.error` | After any red action-bar error (no permission, target not found, already banned/muted, etc). |
| `gui.click` | GUI click feedback (navigation, filter/sort cycle, entry click). |
| `ban.staff-issued` | To the staff member on a successful `/ban`. |
| `ban.staff-unban` | To the staff member on a successful `/unban`. |
| `mute.staff-issued` | To the staff member on a successful `/mute`. |
| `mute.staff-unmute` | To the staff member on a successful `/unmute`. |
| `mute.target-blocked` | To the muted player when they attempt to chat, run a blocked command, edit a sign, write in a book, or rename in an anvil. |
| `warn.staff-issued` | To the staff member on `/warn`. |
| `warn.staff-unwarn` | To the staff member on `/unwarn`. |
| `warn.target-notify` | To the warned player when the warn is applied. |
| `kick.staff-issued` | To the staff member on `/kick`. |
| `refund.take` | To the staff member on every successful take in the `/refund` View GUI. |
| `refund.replace` | To the staff member on a successful Replace in the `/refund` action menu (local, remote, or offline). |
| `refund.giveout` | To the staff member on a successful Give-Out in the `/refund` action menu. |
| `refund.teleport` | To the staff member on a successful same-server Teleport in the `/refund` action menu. Cross-server teleports use the standard teleports feature and its own sounds. |
