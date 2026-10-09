# `commands/fakes.yml`

Location: `plugins/StaffCore/commands/fakes.yml`

Custom responses for `/pl`, `/version` and `/help`, plus the plugin
list players see when they tab-complete those commands. Loaded together
with [`config.yml`](config.md); the two are one feature split across
two files for readability.

## Three replacement handlers

Each handler intercepts a small set of command names, cancels the
vanilla command and sends its own message instead.

- `fake-pl` — replaces `/pl`, `/plugins`, `/icanhasbukkit`, `/?`.
- `fake-version` — replaces `/version`, `/ver`, `/about`.
- `fake-help` — replaces `/help`.

Common shape for all three:

```yaml
enabled: true
message: "..."
commands:
  - pl
  - plugins
```

- `enabled: false` disables the handler completely. The vanilla command
  runs as usual.
- `message` supports legacy `&` colours, `&#RRGGBB` hex and `\n` for
  line breaks. Empty message also disables the handler.
- `commands` lists which command roots the handler catches. Root names
  only, no leading `/`.

Bypass permissions (a staff member with the bypass runs the real
command instead of getting the fake response):

- `staffcore.commands.pl.bypass`
- `staffcore.commands.version.bypass`
- `staffcore.commands.help.bypass`

## fake-profile

Every entry under `fake-profile.plugins` describes one plugin that
appears in the reply when a player tab-completes `/`, `/plugins <arg>`
or `/version <arg>`. Entry fields:

- `name` — display name shown to the client.
- `namespace` — lowercase identifier used as the `<namespace>:command`
  prefix.
- `commands` — list of command roots this fake plugin registers. Root
  names only.
- `subcommands` — optional map of `command: [arg, arg, ...]` used when
  the player tab-completes an argument.
- `anticheat: true` — marks the entry as an anticheat.

`fake-profile.enabled: false` disables the tab-complete response
entirely and returns nothing.

The plugin names in `fake-pl.message` and the entries under
`fake-profile.plugins` should stay in sync so `/pl` and the tab-complete
list agree on what is installed.

## File shape

```yaml
fake-pl:
  enabled: true
  message: "&#00A4FCⓘ &fServer Plugins &8(&f39&8):\n&#00A4FCPaper Plugins &8(&f2&8):\n&8- &aFancyHolograms&f, &aFancyNpcs\n&#FF960CBukkit Plugins &8(&f37&8):\n&8- &aAxAuctions&f, &aAxGraves&f, &aAxMinions&f, &aAxPlayerWarps&f, &aAxShulkers&f, &aAxTrade&f,\n&aAxVaults&f, &aChunky&f, &aCitizens&f, &aCoreProtect&f, &aDeluxeMenus&f, &aDonutCrates&f,\n&aDonutOrders&f, &aDonutShop&f, &aDonutSpawners&f, &aDonutStats&f, &aDonutTags&f, &aDonutWealth&f,\n&aEconomyShopGUI&f, &aEssentialsX&f, &aEssentialsXChat&f, &aEssentialsXSpawn&f, &aHeadDatabase&f,\n&aLiteBans&f, &aLuckPerms&f, &aMultiverse-Core&f, &aPlaceholderAPI&f, &aProtocolLib&f,\n&aSkinsRestorer&f, &aTAB&f, &aVault&f, &aViaBackwards&f, &aViaVersion&f, &aVotifier&f,\n&aVulcan&f, &aWorldEdit&f, &aWorldGuard&f, &amcMMO"
  commands:
    - pl
    - plugins
    - icanhasbukkit
    - "?"

fake-version:
  enabled: true
  message: "&fThis server is running &fUniverseSpigot &fversion &fgit-UniverseSpigot-42 &8(&fMC: 1.21.8&8) &8(&fImplementing API version 1.21.8-R0.1-SNAPSHOT&8)"
  commands:
    - ver
    - version
    - about

fake-help:
  enabled: true
  message: |-
    &#00A4FCⓘ &fHelp
    &7Use &f/rtp&7, &f/spawn&7, &f/warp&7 or ask staff.
  commands:
    - help

fake-profile:
  enabled: true
  plugins:
    fancyholograms:
      name: "FancyHolograms"
      namespace: "fancyholograms"
      commands: [hologram, holograms, fh]
      subcommands:
        hologram: [create, delete, edit, help, info, list, reload, teleport]
    fancynpcs:
      name: "FancyNpcs"
      namespace: "fancynpcs"
      commands: [npc, npcs, fn]
      subcommands:
        npc: [create, remove, edit, list, reload, teleport]
    axauctions:
      name: "AxAuctions"
      namespace: "axauctions"
      commands: [axauctions, ah, auction, auctions]
      subcommands:
        axauctions: [help, reload, sell, list]
    axgraves:
      name: "AxGraves"
      namespace: "axgraves"
      commands: [axgraves]
      subcommands:
        axgraves: [help, reload, list]
    axminions:
      name: "AxMinions"
      namespace: "axminions"
      commands: [axminions, minions]
      subcommands:
        axminions: [help, reload, give, giveall]
    axplayerwarps:
      name: "AxPlayerWarps"
      namespace: "axplayerwarps"
      commands: [axplayerwarps, pwarp, pwarps]
      subcommands:
        axplayerwarps: [help, reload, list]
    axshulkers:
      name: "AxShulkers"
      namespace: "axshulkers"
      commands: [axshulkers, shulker]
      subcommands:
        axshulkers: [help, reload]
    axtrade:
      name: "AxTrade"
      namespace: "axtrade"
      commands: [axtrade, trade]
      subcommands:
        axtrade: [help, reload, request, accept, deny]
    axvaults:
      name: "AxVaults"
      namespace: "axvaults"
      commands: [axvaults, vault, vaults]
      subcommands:
        axvaults: [help, reload, open]
    chunky:
      name: "Chunky"
      namespace: "chunky"
      commands: [chunky]
      subcommands:
        chunky: [cancel, confirm, continue, help, pause, quiet, radius, reload, start, trim, world, worldborder]
    citizens:
      name: "Citizens"
      namespace: "citizens"
      commands: [citizens, npc, trait, waypoints]
      subcommands:
        citizens: [help, reload, save, debug, info, list, select]
    coreprotect:
      name: "CoreProtect"
      namespace: "coreprotect"
      commands: [co, coreprotect]
      subcommands:
        co: [help, inspect, lookup, rollback, restore, purge, status, reload]
    deluxemenus:
      name: "DeluxeMenus"
      namespace: "deluxemenus"
      commands: [deluxemenus, dm]
      subcommands:
        deluxemenus: [help, reload, open, list, dump]
    donutcrates:
      name: "DonutCrates"
      namespace: "donutcrates"
      commands: [donutcrates, crate, crates]
      subcommands:
        donutcrates: [help, reload, give, open]
    donutorders:
      name: "DonutOrders"
      namespace: "donutorders"
      commands: [donutorders, order, orders]
      subcommands:
        donutorders: [help, reload, create, list]
    donutshop:
      name: "DonutShop"
      namespace: "donutshop"
      commands: [donutshop, shop]
      subcommands:
        donutshop: [help, reload]
    donutspawners:
      name: "DonutSpawners"
      namespace: "donutspawners"
      commands: [donutspawners, spawner, spawners]
      subcommands:
        donutspawners: [help, reload, give]
    donutstats:
      name: "DonutStats"
      namespace: "donutstats"
      commands: [donutstats, stats]
      subcommands:
        donutstats: [help, reload, view]
    donuttags:
      name: "DonutTags"
      namespace: "donuttags"
      commands: [donuttags, tag, tags]
      subcommands:
        donuttags: [help, reload, give]
    donutwealth:
      name: "DonutWealth"
      namespace: "donutwealth"
      commands: [donutwealth, wealth, baltop]
      subcommands:
        donutwealth: [help, reload]
    economyshopgui:
      name: "EconomyShopGUI"
      namespace: "economyshopgui"
      commands: [economyshopgui, shop, sell, sellgui, worth]
      subcommands:
        economyshopgui: [help, reload, shop]
    essentialsx:
      name: "EssentialsX"
      namespace: "essentials"
      commands: [essentials, ess]
      subcommands:
        essentials: [cleanup, debug, help, reload, reset, userlist, worth]
    essentialsxchat:
      name: "EssentialsXChat"
      namespace: "essentialschat"
      commands: [essentialschat]
      subcommands:
        essentialschat: [reload, help]
    essentialsxspawn:
      name: "EssentialsXSpawn"
      namespace: "essentialsspawn"
      commands: [essentialsspawn, setspawn]
      subcommands:
        essentialsspawn: [reload, help]
    headdatabase:
      name: "HeadDatabase"
      namespace: "headdatabase"
      commands: [headdatabase, hdb, head, heads]
      subcommands:
        hdb: [help, reload, search, open, give]
    litebans:
      name: "LiteBans"
      namespace: "litebans"
      commands: [litebans, ban, tempban, mute, tempmute, warn, kick, unban, unmute, history]
      subcommands:
        litebans: [help, reload, importer, info]
    luckperms:
      name: "LuckPerms"
      namespace: "luckperms"
      commands: [lp, luckperms, perm, perms, permission, permissions]
      subcommands:
        lp: [user, group, track, sync, reloadconfig, info, verbose, log, import, export]
        luckperms: [user, group, track, sync, reloadconfig, info, verbose, log, import, export]
    multiverse-core:
      name: "Multiverse-Core"
      namespace: "multiverse-core"
      commands: [mv, multiverse, mvcreate, mvdelete, mvimport, mvtp, mvlist]
      subcommands:
        mv: [create, delete, import, load, unload, tp, list, info, reload]
    placeholderapi:
      name: "PlaceholderAPI"
      namespace: "placeholderapi"
      commands: [papi, placeholderapi]
      subcommands:
        papi: [reload, list, info, parse, ecloud, register, unregister]
        placeholderapi: [reload, list, info, parse, ecloud, register, unregister]
    protocollib:
      name: "ProtocolLib"
      namespace: "protocollib"
      commands: [protocol, protocollib]
      subcommands:
        protocol: [config, debug, dump, listeners, logging, packet, reload, timings, version]
    skinsrestorer:
      name: "SkinsRestorer"
      namespace: "skinsrestorer"
      commands: [skinsrestorer, sr, skin]
      subcommands:
        sr: [help, reload, status, drop, update, props, applyskin, createcustom, setskinall, purgeolddata]
        skin: [set, url, clear, update, search, menu]
    tab:
      name: "TAB"
      namespace: "tab"
      commands: [tab, tabinfo, btab]
      subcommands:
        tab: [reload, group, player, debug, cpu, parse, sendtoall]
    vault:
      name: "Vault"
      namespace: "vault"
      commands: [vault-info, vault]
      subcommands:
        vault-info: [info]
    viabackwards:
      name: "ViaBackwards"
      namespace: "viabackwards"
      commands: [viabackwards]
      subcommands:
        viabackwards: [help, reload]
    viaversion:
      name: "ViaVersion"
      namespace: "viaversion"
      commands: [viaversion, vv]
      subcommands:
        viaversion: [help, reload, list, dump, debug, autoteam]
    votifier:
      name: "Votifier"
      namespace: "votifier"
      commands: [votifier, nvreload, testvote]
      subcommands:
        votifier: [reload]
    worldedit:
      name: "WorldEdit"
      namespace: "worldedit"
      commands: [worldedit, we, "/wand", toggleeditwand, "/undo", "/redo", "/pos1", "/pos2", "/copy", "/paste", "/cut", "/rotate", "/set", "/replace"]
      subcommands:
        worldedit: [help, reload, version, cui, trace, tz]
    worldguard:
      name: "WorldGuard"
      namespace: "worldguard"
      commands: [wg, worldguard, region, rg]
      subcommands:
        wg: [reload, report, flushstates, running, version, debug]
        region: [define, redefine, claim, flag, info, list, remove, addmember, removemember, addowner, removeowner]
    mcmmo:
      name: "mcMMO"
      namespace: "mcmmo"
      commands: [mcmmo, skillreset, mcability, mcstats, mctop, party, ptp]
      subcommands:
        mcmmo: [help, reload, mmoedit, mmoupdate, mmoinfo, mcability, mcstats]
    vulcan:
      name: "Vulcan"
      namespace: "vulcan"
      commands: [vulcan, vl]
      subcommands:
        vulcan: [help, reload, alerts, logs, verbose, info, punishments, version, resetviolations]
      anticheat: true
```
