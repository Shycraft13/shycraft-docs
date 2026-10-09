# `inspect/config.yml`

Location: `plugins/StaffCore/inspect/config.yml`

Behaviour of the inventory viewer (`/invsee`, `/echestsee`). The feature as a
whole is gated by `features.inspect` in `config/config.yml`; with that toggle off
everything below is ignored.

```yaml
inspect:

  cross-server: true

  snapshot-ttl-seconds: 60

  apply-ttl-seconds: 60

  reply-timeout-ms: 3000

  live-sync:
    local-refresh-ticks: 3

    local-apply-ticks: 2

    cross-refresh-ticks: 20

    cross-apply-ticks: 10
```
