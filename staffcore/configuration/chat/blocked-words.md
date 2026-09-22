# `chat/blocked-words.yml`

Location: `plugins/StaffCore/chat/blocked-words.yml`

Anti-swear filter. Runs on every non-muted chat message and (when the
matching context is on) on signs, books and anvil renames. Command
availability is gated by `features.chat` in
[`config/config.yml`](../config/config.md); this file tunes what counts
as a banned word, how to normalise input before matching, and what to
do on a match.

`staffcore.chat.bypass` and `staffcore.admin` skip the anti-swear check
in every context. Muted players never reach the check either, because
mutes are cancelled upstream.

```yaml
ENABLED: true

ACTION: BLOCK
MUTE-DURATION: 30m
MUTE-REASON: "Inappropriate language."
WARN-REASON: "Inappropriate language."
KICK-REASON: "Inappropriate language."
BLOCK-MESSAGE: "&cThat message contains a blocked word."

CHECK:
  chat: true
  sign: true
  book: true
  anvil: true

NORMALIZATION:
  strip-diacritics: true
  leet-substitution: true
  strip-non-letters: true
  collapse-repeats: false

MIN-WORD-LENGTH: 3

WHITELIST:
  - "analysis"
  - "class"
  - "password"
  # ... 55 defaults shipped

WORDS:
  - "example"
  # ... shipped with the merged LDNOOBW en + de list (~465 entries)
```

## Keys

| Key | Default | Description |
| --- | --- | --- |
| `ENABLED` | `true` | Master switch for the anti-swear filter. When `false`, no scan runs in any context. |
| `ACTION` | `BLOCK` | What to do on a match. One of `BLOCK`, `MUTE`, `WARN`, `KICK`. See [Actions](#actions). |
| `MUTE-DURATION` | `30m` | Duration for `ACTION: MUTE`. Supports `1s`, `1m`, `1h`, `1d`, `1w`, combinations like `1d2h`, plus `perm` / `permanent` / `forever` for a permanent mute. |
| `MUTE-REASON` | `"Inappropriate language."` | Reason shown to the muted player and stored in history. |
| `WARN-REASON` | `"Inappropriate language."` | Reason stored on the warn record. |
| `KICK-REASON` | `"Inappropriate language."` | Kick screen for `ACTION: KICK`. Supports legacy `&` and `&#RRGGBB` hex. |
| `BLOCK-MESSAGE` | `"&cThat message contains a blocked word."` | Feedback sent to the offender on any match, on the **action bar** so it doesn't spam the chat log. Always fires, regardless of `ACTION`. |
| `CHECK.chat` | `true` | Scan chat messages. |
| `CHECK.sign` | `true` | Scan every line of a placed / edited sign. |
| `CHECK.book` | `true` | Scan the title + every page of a written book. |
| `CHECK.anvil` | `true` | Scan the anvil rename box. On a hit, the anvil result is nulled and the action fires when the player tries to take it. |
| `NORMALIZATION.strip-diacritics` | `true` | Strip accents before matching (`fück` → `fuck`). |
| `NORMALIZATION.leet-substitution` | `true` | Replace common leet characters before matching (`0`→`o`, `1`→`i`, `3`→`e`, `4`→`a`, `5`→`s`, `7`→`t`, `8`→`b`, `9`→`g`, `@`→`a`, `$`→`s`, `!`→`i`, `+`→`t`, `\|`→`i`). |
| `NORMALIZATION.strip-non-letters` | `true` | Drop whitespace, digits and punctuation after leet mapping. `s h i t` → `shit`, `f.u.c.k` → `fuck`. |
| `NORMALIZATION.collapse-repeats` | `false` | Collapse runs of the same letter to one (`fuuuck` → `fuck`). Off by default because it creates more false positives (`bass` → `bas` triggers `ass`). |
| `MIN-WORD-LENGTH` | `3` | Banned entries shorter than this length AFTER normalisation are ignored. Raise to `4` if you still see false positives from 3-letter entries. |
| `WHITELIST` | 55 defaults | Innocent words that happen to contain a banned substring. Every occurrence is masked out of the message BEFORE the scan, so its letters can never contribute to a match. Add more when you hit a false positive. |
| `WORDS` | ~465 defaults | The banned-word list. Merged and lowercased from [LDNOOBW](https://github.com/LDNOOBW/List-of-Dirty-Naughty-Obscene-and-Otherwise-Bad-Words) `en` + `de`. Edit freely: add, remove, replace. Multi-word entries (e.g. `- "hot carl"`) are also normalised, so a player can't dodge one by adding punctuation between the tokens. |

## Actions

| Action | Effect |
| --- | --- |
| `BLOCK` | Cancel the event, send `BLOCK-MESSAGE` on the action bar. Nothing else. |
| `MUTE` | `BLOCK` + mute the player for `MUTE-DURATION` through the staffcore mute pipeline. Cross-server propagates through the same channel as `/mute`. Requires `features.punishments: true`; degrades to `BLOCK` (with a console warning) when the punishments feature is off. |
| `WARN` | `BLOCK` + add one warn to the player's history via the staffcore warn pipeline. Requires `features.punishments: true`; degrades to `BLOCK` when off. |
| `KICK` | `BLOCK` + kick the player with `KICK-REASON` as the disconnect screen. |

The staff name attached to auto-mutes and auto-warns is `AntiSwear` (UUID
all zeros) so they are easy to filter out of history queries.

## How matching works

1. The input is lowercased.
2. Diacritics are stripped (if `strip-diacritics: true`).
3. Leet characters are replaced (if `leet-substitution: true`).
4. Everything that is not a letter is dropped (if `strip-non-letters: true`).
5. Runs of the same letter are collapsed to a single letter (if `collapse-repeats: true`).
6. Every `WHITELIST` entry is normalised the same way and masked out of
   the input (replaced with a spacer that can't match a banned word).
7. Every `WORDS` entry is normalised. Entries shorter than
   `MIN-WORD-LENGTH` after normalisation are ignored. The first entry
   whose normalised form appears as a substring of the masked input
   wins; the action fires and the scan stops.

Because the scan runs on a fully normalised letter-only run, common
bypasses collapse to the same string as the plain form: `Sh!t`,
`s h i t`, `sh1t`, `SHIT!!!` and `shììt` all match one entry for `shit`.

## Bypass vs false positives

There is no configuration that eliminates both. The shipped defaults
favour precision over recall — turn the knobs to shift the trade-off:

- More strict (catches more bypass attempts, more false positives):
  turn `collapse-repeats` on, lower `MIN-WORD-LENGTH` to `2`.
- More lenient (fewer false flags, easier to bypass): turn
  `leet-substitution` off (keeps letters intact), raise
  `MIN-WORD-LENGTH` to `4`, add the false-flagging word to
  `WHITELIST`.

The `WHITELIST` is by far the highest-leverage knob. Adding a single
entry (`"password"`) removes an entire false-positive class without
weakening the scan for anyone else.

## Interaction with `features.chat`

If `features.chat: false` in [`config/config.yml`](../config/config.md),
neither the chat filters nor the anti-swear listeners are registered on
this backend. The keys in this file are ignored until the master switch
is on.

## Interaction with `features.punishments`

`ACTION: MUTE` and `ACTION: WARN` reuse the staffcore mute / warn
services. When `features.punishments: false`, those services are not
initialised, and the anti-swear filter falls back to `BLOCK` with a
warning in the console log. `ACTION: BLOCK` and `ACTION: KICK` do not
depend on the punishments feature.

## Reload

`/staffcore reload` re-reads this file and applies every value on the
next event. Existing mutes / warns already written by the anti-swear
filter are not affected (they live in the punishment store like any
other mute / warn).
