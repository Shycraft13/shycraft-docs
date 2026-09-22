# `refund/config.yml`

Location: `plugins/StaffCore/refund/config.yml`

Behaviour of the `/refund` feature: how many snapshots to keep per player,
which capture triggers are active, and the cross-server switch.

```yaml
refund:
  max-per-category: 10
  cross-server: true
  payload-ttl-seconds: 60

  capture:
    death: true
    join: true
    quit: true
    enderchest: true
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `refund.max-per-category` | `10` | Rolling retention per (player, category). When a new snapshot is inserted, the oldest ones beyond this cap are pruned in the same transaction. Keep this small: every snapshot stores the full item payload, so 10 is already generous for most staff use cases. |
| `refund.cross-server` | `true` | Per-feature gate on top of the network-wide `cross-server.enabled` in [`config/config.yml`](../config/config.md). BOTH must be on for staff to replace / teleport to snapshots whose target is on another backend. When off, `/refund` only works locally. |
| `refund.payload-ttl-seconds` | `60` | How long an in-flight refund payload stays parked in Redis before it's evicted. Only matters if the requesting server crashes between announce and consume: raising this keeps the payload alive longer for that rare recovery, at the cost of a stale item copy hanging around. |
| `refund.capture.death` | `true` | Snapshot the target's inventory when they die. Runs after other plugins have adjusted the death drop (keep-inventory, plugin-managed loot). |
| `refund.capture.join` | `true` | Snapshot the target's inventory the moment they log in. Useful for detecting item losses caused by another plugin's join handler. |
| `refund.capture.quit` | `true` | Snapshot the target's inventory the moment they log out. |
| `refund.capture.enderchest` | `true` | Snapshot the target's enderchest whenever they close it. |

Turning a capture trigger off stops new snapshots for that category. Existing
snapshots stay browsable in the GUI until they age out under
`max-per-category`.
