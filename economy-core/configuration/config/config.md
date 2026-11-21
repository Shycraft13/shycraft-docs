# `config/config.yml`

Location: `plugins/EconomyCore/config/config.yml`

```yaml
license:
  key: "LIC-XXXXXXXX-XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"

world-names:
  world: "overworld"
  world_nether: "nether"
  world_the_end: "end"

debug: false

chat-messages: true
actionbar-messages: true

features:
  pay: true
  homes: true
  tpa: true
  rtp: true
  sell: true
  worth: true
  shop: true
  statistics: true
  leaderboard: true
  bounty: true
  team: true
  combat: true
  keyall: true
  chat: true
  spawn: true
  warp: true
  afk: true
  rtpzone: true
  rtpqueue: true
  announcement: true
  menus: true
  kits: true
  tags: true
  util: true
```

`chat-messages` and `actionbar-messages` decide where the plugin's one-line messages
appear: in chat (with their prefix), on the action bar (without it), or both. Setting
one to `false` turns that channel off for every player. With both on, each player can
still turn either one off for themselves in `/settings` ("Chat Messages", "Action Bar
Messages"). Errors show in red on the action bar and as `ERROR » <text>` in chat.
Longer output such as help pages, lists and announcements always goes to chat. A
message left empty (`""`) in a messages file is not sent at all.
