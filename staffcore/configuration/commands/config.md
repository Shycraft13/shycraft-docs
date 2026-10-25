# `commands/config.yml`

Location: `plugins/StaffCore/commands/config.yml`

Per-group command visibility and execution filter. Restricts which
commands each player can see in tab-complete and which ones they can
actually run, based on the permission group they hold. Gated by
`features.commands` in [`config/config.yml`](../config/config.md).

Sister files in the same folder:

- [`fakes.yml`](fakes.md) — replacement responses for `/pl`, `/version`
  and `/help`.
- [`leak-hide.yml`](leak-hide.md) — extra visibility toggles.

## How groups work

Every player resolves to exactly one group. The group is picked by
permission (`staffcore.commands.group.<name>`); if a player holds
several, the group with the highest `priority` wins. Players without a
group permission fall through to `default`.

Each group carries four independent lists:

- `tab-complete` — which command roots appear when the player presses
  TAB. Anything not in the list is hidden.
- `execute` — which command roots the player is allowed to run. A
  command in `execute` but not `tab-complete` runs when typed but does
  not appear in tab.
- `deny-tab-complete` / `deny-execute` — override the allow list, deny
  always wins (even over `"*"`).

`"*"` in an allow list means "allow every command". Deny lists then
punch specific holes.

## Inheritance

Groups can chain via `inherits: <parent>`. Parent lists are folded into
the child before the child's own additions and denies apply:

- A child listing a command in its own allow list lifts the parent's
  deny for that command.
- A child using `"*"` in its allow list wipes every inherited deny for
  that axis.
- Cycles are broken silently.

## Blocked-message

Shown when the player tries to run a command they cannot use, or when
they type a command that does not exist. The two cases share the same
message so a player cannot tell them apart.

- `blocked-message-actionbar: true` sends the text to the action bar
  (brief, no chat clutter). `false` sends it to chat.
- Group-level `blocked-message` overrides the global one. An empty
  string means silent block (no message at all).
- `%command%` in the template is replaced with the root the player
  typed.

## Fake brand

Sets the server "brand" string the client shows in its F3 debug
overlay. Rewrites the outgoing brand payload to `fake-brand.value`.
Empty `value` disables the rewrite even when `enabled: true`.

Bypass permission: `staffcore.commands.brand.bypass` — a staff member
with the bypass sees the real brand.

## Rate limit

`tab-rate-limit-per-second` caps how many tab-complete requests per
second a single player can generate. Burst requests above the cap get
an empty response. Set to `0` to disable the cap. Real players tab at
maybe four to five times a second, the default of `60` leaves a wide
safety margin.

## File shape

```yaml
blocked-message: "&cThis command does not exist"

blocked-message-actionbar: true

fake-brand:
  enabled: true
  value: "UniverseSpigot"

tab-rate-limit-per-second: 60

groups:
  default:
    priority: 0
    tab-complete:
      - rtp
      - rtpqueue
      - team
      - spawn
      - tpa
      - tpaccept
      - tpdeny
      - warp
      - warps
      - home
      - homes
      - sethome
      - delhome
      - pay
      - money
      - bal
      - balance
      - baltop
      - worth
      - shop
      - sell
      - sellmulti
      - sellhand
      - sellall
      - buy
      - ah
      - auction
      - order
      - orders
      - msg
      - tell
      - whisper
      - r
      - reply
      - afk
      - settings
      - kit
      - kits
      - tag
      - tags
      - leaderboard
      - leaderboards
      - bounty
      - bounties
      - report
    execute:
      - rtp
      - rtpqueue
      - team
      - spawn
      - tpa
      - tpaccept
      - tpdeny
      - warp
      - warps
      - home
      - homes
      - sethome
      - delhome
      - back
      - pay
      - money
      - bal
      - balance
      - baltop
      - worth
      - shop
      - sell
      - sellmulti
      - sellhand
      - sellall
      - buy
      - ah
      - auction
      - order
      - orders
      - msg
      - tell
      - whisper
      - r
      - reply
      - afk
      - settings
      - kit
      - kits
      - tag
      - tags
      - leaderboard
      - leaderboards
      - bounty
      - bounties
      - report

  staff:
    priority: 5
    inherits: [default]
    staff: true

  helper:
    priority: 10
    inherits: [staff]
    staff-commands:
      - staffchat
      - warn
      - mute
      - server
      - glist
      - send
      - find

  mod:
    priority: 20
    inherits: [helper]
    staff-commands:
      - kick
      - unwarn
      - unmute
      - freeze
      - vanish
      - v
      - invsee

  admin:
    priority: 50
    inherits: [mod]
    staff-commands:
      - ban
      - tempban
      - unban
      - punish
      - tp
      - tphere
      - tppos
      - spectate
      - gamemode
      - gm
      - gms
      - gmc
      - gma
      - gmsp
      - fly
      - flyspeed
      - speed
      - heal
      - feed
      - repair
      - near
      - top
      - refund
      - endersee
      - alts
      - history
      - warns
      - reports
      - spy
      - staffclear

  owner:
    priority: 100
    inherits: [admin]
    staff-commands: ["*"]
    staffmode-show-namespaced: true
    staffmode-show-always-hidden: true
```
