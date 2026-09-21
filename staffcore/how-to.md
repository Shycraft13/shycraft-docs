# How-to Guides

Quick walkthroughs for the most common admin tasks.

## Ban a player

**Permanent, no reason:**
```
/ban Steve
```

**Permanent with reason:**
```
/ban Steve Cheating detected on stream.
```

**Temporary:**
```
/ban Steve 3d Multi-account exploit.
```

**Kill the target on the way out** (drops items, counts toward stats):
```
/ban Steve 7d Griefing spawn. --kill
```

The `--kill` flag can appear anywhere in the command. It is stripped from the recorded reason.

## Unban a player

Regular unban (the ban counts toward the template ladder as time served):
```
/unban Steve
```

The ban was a mistake and should not count toward the ladder:
```
/unban Steve --void
```

`/pardon` is an alias for `/unban`.

## Mute a player

Same syntax as bans:
```
/mute Steve 1h Spamming in chat.
```

The mute record blocks:
- Chat messages
- `/msg`, `/reply` and every other configured whisper command
- Sign edits
- Book writing
- Anvil renames
- Simple Voice Chat microphone (if the plugin is installed)

Configure which commands and channels are blocked in [`punishments/config.yml`](configuration/punishments/config.md) under `mute:`.

## Use a template

Open the GUI to pick a template interactively:
```
/punish Steve
```

Apply a specific template directly:
```
/punish Steve cheating
```

The tier is decided automatically based on how many times Steve has been punished with this template inside its `expire-ladder` window. First offence = `first` step, second = `second`, and so on. See [Punishment Templates](templates.md) for the full model.

For BAN-category templates you can add `--kill`:
```
/punish Steve cheating --kill
```

## View a player's history

```
/history Steve
```

Opens the GUI. Filter by ban / mute / warn / kick with the top-row filter item, sort newest-first / oldest-first with the sort item. Each entry shows:

- **Still active** with remaining time (or `permanent`).
- **Expired** with the past expiry date, for punishments that ran out on their own.
- **Lifted** with the staff member and lift date, for punishments that were manually removed via `/unban` or `/unmute`.

## Check for alt accounts

```
/alts Steve
```

Every account that has shared an IP with Steve gets a slot in the GUI, colour-coded:

- **Green** = currently online (on any backend).
- **Grey** = offline.
- **Red** = banned.

Sort is online → banned → offline, ties broken by most recent seen. IPs themselves are counted but never displayed (screen-share safety). Query the database directly if you need the raw addresses.

## Remove a warn

Every warn has a short 6-character id, visible in `/warns` and `/history`:

```
/warns Steve
```

Remove one by id:
```
/unwarn Steve abc123
```

Void it instead (row stays in history but no longer counts toward the ladder):
```
/unwarn Steve abc123 --void
```

## Add a new punishment template

1. Open `plugins/StaffCore/punishments/punishments.yml`.
2. Pick a category (`ban-templates`, `mute-templates`, `warn-templates`, `kick-templates`).
3. Add a new entry:
   ```yaml
   ban-templates:
     mycategory:
       reason: 'My reason'
       permission: staffcore.template.mycategory
       expire-ladder: 90d
       ladder:
         first:
           duration: 3d
         second:
           duration: 7d
   ```
4. Add the permission node to `plugins/StaffCore/config/permissions.yml`:
   ```yaml
   permissions:
     - staffcore.template.mycategory
   ```
5. Run `/staffcore reload`.
6. Grant the permission to the staff members who should be able to use it.

## Push configs to every node

On a multi-server network, after you edit `punishments/messages.yml` on one node and want every other node to receive the same file:

**Interactive:**
```
/staffcore push
```

Pick target servers, pick preset `gui` (or `punishments` or `all`), confirm.

**Scripted:**
```
/staffcore push * punishments
```

Copies the whole `punishments/` folder from your current node to every other node. Then run `/staffcore reload` on each target node, or restart it.

Requires Redis enabled network-wide.

## Reload configs

```
/staffcore reload
```

Re-reads every YAML under `plugins/StaffCore/`. Templates are re-parsed, message cache flushed. Database connections and event listeners are not restarted; changes to the chat-interception toggle in `mute.intercept-with-packetevents` require a server restart to apply.

## Grant a staff rank the "moderator" set

Typical permission set for a moderator role (via your permission plugin):

```
staffcore.use
staffcore.notify
staffcore.ban
staffcore.ban.temp
staffcore.unban
staffcore.mute
staffcore.mute.temp
staffcore.unmute
staffcore.warn
staffcore.warns
staffcore.unwarn
staffcore.kick
staffcore.punish
staffcore.template.spam
staffcore.template.advertising
staffcore.template.minorspam
staffcore.template.behavior
staffcore.alts
```

For an "admin" role add `staffcore.admin` plus every remaining `staffcore.template.*` and `staffcore.ban.permanent` / `staffcore.mute.permanent`. See [Permissions](permissions.md) for the full node list.

## Migrate templates from LiteBans

The template model is a close match. To port:

1. Copy the template names, reasons, ladder steps and durations over.
2. Rename every `$name` placeholder to `%name%` (e.g. `$player` → `%player%`, `$reason` → `%reason%`).
3. Note that staffcore doesn't currently support LiteBans-style `template-groups`. If your source uses them, flatten into standalone templates first.
4. Set every template's `permission:` to something starting with `staffcore.template.` for consistency, and register the node in `config/permissions.yml`.
