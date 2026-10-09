# `economy/shards/config.yml`

Location: `plugins/EconomyCore/economy/shards/config.yml`

> Servers upgrading from an older build: on first start after the update, the
> plugin renames the existing `economy/afk/` folder to `economy/shards/`
> automatically. Your edits are preserved. No manual copy is required.

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

pay:
  enabled: false
  commands: ["shardspay"]
  permission: ""
  min-amount: 1
  max-amount: 100000000000000
  cooldown-seconds: 1
```
