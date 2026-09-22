# Permissions

RayGuard Enterprise ships three permission nodes. All default to `op`.

| Node | Default | Description |
| --- | --- | --- |
| `rayguardenterprise.bypass` | `op` | See the raw, unfiltered world. Anti-x-ray, anti-freecam, tile culling and entity culling all skip a bypassed player. Useful for admins verifying what really is in the ground, and for testing the fake world with the `/rayguard fake` commands. |
| `rayguardenterprise.reload` | `op` | Use `/rayguard reload`. |
| `rayguardenterprise.fakeworld` | `op` | Use the `/rayguard fake` subcommands. Additionally requires `developer-mode: true` in `config.yml`. |

## Bypass and cheating staff

The bypass permission is intentionally the only "unhide" toggle. A staff member with `rayguardenterprise.bypass` sees the real ores and the real underground, which is exactly what a cheater sees on a server without the plugin. Grant it only to staff you would trust with the raw world anyway.

Bypass status is refreshed on every login, on every LuckPerms group change (if LuckPerms is installed), and on `/rayguard reload`. Revoking the permission removes the bypass on the next scan tick (well under one second).
