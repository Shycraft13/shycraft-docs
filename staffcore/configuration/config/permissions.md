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
  - staffcore.unban

  - staffcore.mute
  - staffcore.mute.temp
  - staffcore.mute.permanent
  - staffcore.mute.bypass
  - staffcore.unmute

  - staffcore.warn
  - staffcore.warn.bypass
  - staffcore.unwarn
  - staffcore.warns

  - staffcore.kick
  - staffcore.kick.bypass

  - staffcore.punish

  - staffcore.alts

  - staffcore.reload

  - staffcore.template.cheating
  - staffcore.template.xray
  - staffcore.template.exploiting
  - staffcore.template.spam
  - staffcore.template.threats
  - staffcore.template.advertising
  - staffcore.template.minorspam
  - staffcore.template.behavior
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
