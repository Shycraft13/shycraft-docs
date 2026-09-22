# Installation

## Requirements

- **Server software**: Paper 1.21 or newer (or a Paper fork, Folia supported).
- **Java**: 21 or newer.
- **PacketEvents plugin**: required. Grab the latest release from [Modrinth](https://modrinth.com/plugin/packetevents) or SpigotMC and drop it into `plugins/`.
- **LuckPerms**: optional. If present, the bypass permission is checked through LuckPerms.
- **A RayGuard Enterprise license key** from BuiltByBit. See [Getting a license key](#getting-a-license-key).

## Getting a license key

1. Buy RayGuard Enterprise on BuiltByBit.
2. Link your Discord account in your BuiltByBit profile if you have not already (Profile → Preferences → External Accounts → Discord).
3. Join the [Shycraft Discord](https://discord.gg/MSzB5AxqRp).
4. Within about a minute the `Shys Helper` bot will DM you your license key along with these installation instructions.

If you did not receive a DM:

- Check that your Discord DMs are open for the Shycraft server (Server Settings → Privacy Settings → Direct Messages).
- Run `/mylicense` on the Shycraft Discord. This lists every key issued to you and shows the full key value.
- If you still cannot see a key for RayGuard Enterprise, open a **License Support** ticket on the Shycraft Discord.

## Install

1. Stop your server.
2. Drop `PacketEvents-<version>.jar` and `RayGuard-Enterprise-<version>.jar` into `plugins/`.
3. Start the server once. The plugin will refuse to start with a clear console message because the license key has not been set yet. The default `plugins/RayGuard-Enterprise/config.yml` was written.
4. Stop the server.
5. Open `plugins/RayGuard-Enterprise/config.yml` and paste your key under `license.key`:

   ```yaml
   license:
     key: "LIC-XXXXXXXX-XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
   ```
6. Start the server again. Look for `RayGuardEnterprise license OK` in the console.

Every other configuration file (`antifreecam.yml`, `entityculling.yml`, `tileculling.yml`, `anti-xray/`, `chunkprotect.yml`, `fakeworld.yml`, `transparency.yml`) is created on this second start, once the license check passes. Ship-time defaults protect the world named `world` (overworld) and `world_nether` (nether) with sensible values. If your world folders are named differently, edit the `worlds:` block of each feature. See [`configuration/`](configuration/README.md).

## Verifying the license

On startup you should see either:

```
[RayGuardEnterprise] License OK, bound to this machine.
```

or a framed error block explaining exactly what went wrong. Possible outcomes:

| Situation | Result |
| --- | --- |
| Valid key, machine within the license's binding slots | starts |
| Invalid / unknown / wrong-product / revoked key | plugin disabled, console block tells you which |
| Key valid but the machine is not in the binding slots (all slots used) | plugin disabled, run `/ipreset` on Discord to free the slot |
| License server unreachable / HTTP error / DNS failure | plugin disabled (online-only, no offline grace) |

The check is online-only: RayGuard Enterprise contacts `license.shycraft.eu` on every startup. Firewalling that host or blocking outbound HTTPS to it will disable the plugin.

## Upgrading

Drop in the new JAR and restart. Existing configs are preserved: on the next start every config file is rebuilt from the shipped template, but only the *layout* and *comments* are refreshed. Values you have set are never overwritten, and keys the new template does not know about are kept. New options appear at their spot in the template with their explanatory comment.

The bundled fake-world pack `packs/default.rgpack` is always replaced by the pack inside the new JAR, so a fix baked into it reaches every installation. If you baked your own pack under a different name (see [`fakeworld.yml`](configuration/fakeworld.md)), that file is left alone.

## First-run checklist

- PacketEvents is in `plugins/` alongside RayGuard Enterprise.
- Your license key is pasted into `config.yml` and the console prints `License OK` on startup.
- The world names in `antifreecam.yml`, `entityculling.yml`, `tileculling.yml`, `chunkprotect.yml`, and the file names under `anti-xray/` (`world.yml`, `world_nether.yml`, ...) match your actual world folders. Missing worlds are silently unprotected.
- Staff who need to see the raw world for testing have the `rayguardenterprise.bypass` permission.
