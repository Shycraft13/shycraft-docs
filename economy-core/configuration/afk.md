# AFK (`economy/afk/`)

AFK zones, shard rewards for standing in them and shards-on-kill settings.

## `economy/afk/config.yml`

```yaml
afk:
  teleport-delay: 5
  reward:

    enabled: true
    interval-seconds: 60
    shards-per-interval: 1

shards-everywhere:
  enabled: false
  interval-seconds: 60
  shards-per-interval: 1

shards-per-kill:
  enabled: true
  amount: 10
  cooldown-seconds: 86400

  message: "&#A303F9&lSHARDS &r&7» &fYou earned &#A303F9%amount% shards &ffrom killing &#FCE300%player%&f."
```

## `economy/afk/messages.yml`

```yaml
messages:
  no-afk-set: "&cAFK location has not been set yet."
  afk-set: "&#00A4FC&lAFK &r&7» &fAFK location has been set."
  teleporting: "&#00A4FC&lAFK &r&7» &fTeleporting to AFK..."
  already-teleporting: "&cYou are already teleporting."
  zone-created: "&#00A4FC&lAFK &r&7» &fAFK zone &#FCE300%name% &fcreated."
  zone-deleted: "&#00A4FC&lAFK &r&7» &fAFK zone &#FCE300%name% &fdeleted."
  zone-not-found: "&cAFK zone not found."
  wand-given: "&#00A4FC&lAFK &r&7» &fLeft-click to set corner 1, right-click to set corner 2."
  pos1-set: "&#00A4FC&lAFK &r&7» &fCorner 1 set at &#FCE300%x%, %y%, %z%&f."
  pos2-set: "&#00A4FC&lAFK &r&7» &fCorner 2 set at &#FCE300%x%, %y%, %z%&f."
  both-corners-needed: "&cSet both corners first."

  actionbar: "&7Next shard in &#A303F9%time%&7."
  shard-reward: "&#A303F9&lAFK &r&7» &f+&#A303F9%amount% &fshards."
```

## `economy/afk/sounds.yml`

```yaml
sounds:
  teleport: "minecraft:entity.enderman.teleport|1.0|1.0"
  reward: "minecraft:entity.experience_orb.pickup|1.0|1.0"
```

