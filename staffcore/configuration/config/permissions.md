# `config/permissions.yml`

Location: `plugins/StaffCore/config/permissions.yml`

Registry of permission nodes staffcore will register with the server. Every
node has a hardcoded default (`op` or `false`) that cannot be changed from
this file. Remove a line to unregister the node from the server.

The list below is the shipped default. See [Permissions](../../permissions.md)
for what each node grants and its default.

```yaml
permissions:

  - staffcore.use
  - staffcore.admin
  - staffcore.notify

  - staffcore.ban
  - staffcore.ban.temp
  - staffcore.ban.permanent
  - staffcore.ban.bypass
  - staffcore.ban.ip
  - staffcore.unban
  - staffcore.unban.own
  - staffcore.unban.group
  - staffcore.checkban

  - staffcore.mute
  - staffcore.mute.temp
  - staffcore.mute.permanent
  - staffcore.mute.bypass
  - staffcore.mute.ip
  - staffcore.unmute
  - staffcore.unmute.own
  - staffcore.unmute.group
  - staffcore.checkmute

  - staffcore.warn
  - staffcore.warn.bypass
  - staffcore.unwarn
  - staffcore.unwarn.own
  - staffcore.unwarn.group
  - staffcore.warns
  - staffcore.checkwarn

  - staffcore.kick
  - staffcore.kick.bypass

  - staffcore.punish

  - staffcore.alts

  - staffcore.reload

  - staffcore.invsee.use
  - staffcore.invsee.edit
  - staffcore.echestsee.use
  - staffcore.echestsee.edit
  - staffcore.inspect.bypass

  - staffcore.refund.use
  - staffcore.refund.replace
  - staffcore.refund.giveout
  - staffcore.refund.teleport

  - staffcore.gamemode.survival
  - staffcore.gamemode.creative
  - staffcore.gamemode.adventure
  - staffcore.gamemode.spectator
  - staffcore.gamemode.other
  - staffcore.gamemode.offline

  - staffcore.tp
  - staffcore.tphere
  - staffcore.tppos
  - staffcore.back
  - staffcore.randomtp
  - staffcore.tp.offline
  - staffcore.teleport.admin
  - staffcore.tp.bypass

  - staffcore.chat.bypass
  - staffcore.chat.clear
  - staffcore.chat.pause

  - staffcore.announce
  - staffcore.broadcast

  - staffcore.staffchat

  - staffcore.spy

  - staffcore.freeze

  - staffcore.vanish
  - staffcore.vanish.other
  - staffcore.vanish.see

  - staffcore.utils.fly
  - staffcore.utils.fly.other
  - staffcore.utils.flyspeed
  - staffcore.utils.flyspeed.other
  - staffcore.utils.speed
  - staffcore.utils.speed.other
  - staffcore.utils.heal
  - staffcore.utils.heal.other
  - staffcore.utils.feed
  - staffcore.utils.feed.other
  - staffcore.utils.repair
  - staffcore.utils.repair.other
  - staffcore.utils.near
  - staffcore.utils.top

  - staffcore.report
  - staffcore.report.exempt
  - staffcore.reports.review
  - staffcore.report.cooldown-bypass

  - staffcore.limit.bypass
  - staffcore.limit.unlimited
  - staffcore.cooldown.bypass
  - staffcore.cooldown.bypass.ban
  - staffcore.cooldown.bypass.mute
  - staffcore.cooldown.bypass.warn
  - staffcore.cooldown.bypass.kick

  - staffcore.commands.bypass
  - staffcore.commands.pl.bypass
  - staffcore.commands.version.bypass
  - staffcore.commands.help.bypass
  - staffcore.commands.brand.bypass

  - staffcore.staffmode
  - staffcore.staffmode.manage

  - staffcore.maintenance.admin
  - staffcore.maintenance.bypass

  - staffcore.template.ban.basic
  - staffcore.template.mute.basic
  - staffcore.template.warn.basic
  - staffcore.template.kick.basic
  - staffcore.template.ban.severe
  - staffcore.template.mute.severe
  - staffcore.template.admin
```

## Adding a template node

When you add a new template to
[`punishments/punishments.yml`](../punishments/punishments.md), add its
permission node here so it shows up in permission plugins like LuckPerms:

```yaml
permissions:
  - staffcore.template.mycategory
```

The node still works at runtime even if you don't register it here (the plugin
falls back to the hardcoded `op` default). Registering it just makes it
visible to `/lp editor` and similar tools.
