# `chat/config.yml`

Location: `plugins/StaffCore/chat/config.yml`

Server-side chat filters. Runs on every non-muted chat message; mutes are
handled upstream so a muted player never reaches these filters. Command
availability is gated by `features.chat` in
[`config/config.yml`](../config/config.md); this file only tunes each
filter's behaviour.

Every filter has a `.ENABLED` toggle and a `.BLOCK-MESSAGE`. All messages
support legacy `&` colours and `&#RRGGBB` hex.

`staffcore.chat.bypass` and `staffcore.admin` skip every filter and never
count toward the anti-repeat or rate-limit buffers.

```yaml
CHAT:
  LANGUAGE-FILTER:
    ENABLED: true
    ALLOWED-ALPHABETS:
      - LATIN
      - NUMBERS
      - SYMBOLS
    BLOCK-MESSAGE: "&cYour message contains characters that are not allowed."

  ANTI-REPEAT:
    ENABLED: true
    BLOCK-MESSAGE: "&cDon't send the same message twice in a row."

  CAPS-LIMIT:
    ENABLED: false
    MIN-LENGTH: 8
    PERCENT: 70
    BLOCK-MESSAGE: "&cPlease don't shout."

  COOLDOWN:
    ENABLED: false
    SECONDS: 2
    BLOCK-MESSAGE: "&cSlow down. You can chat again in %seconds%s."

  MESSAGE-LIMIT:
    ENABLED: false
    MAX-MESSAGES: 5
    WINDOW-SECONDS: 10
    BLOCK-MESSAGE: "&cYou're sending messages too fast. Try again in %seconds%s."
```

## Filters

### Language filter

Drops messages that contain any character outside the allowed alphabets.
Prevents zalgo, obscure scripts and non-ASCII spam.

| Alphabet | What it matches |
| --- | --- |
| `LATIN` | Basic Latin + Latin-1 Supplement + Latin Extended-A/B (`U+0020..U+024F`). Covers standard ASCII plus accented European letters. |
| `NUMBERS` | Any digit (`Character.isDigit`). |
| `SYMBOLS` | ASCII punctuation ranges plus space and newline. |

Order of the list doesn't matter: a character passes if ANY listed
alphabet matches it.

### Anti-repeat

Blocks a player from sending the same message twice in a row. Comparison
is normalised (lowercase, trimmed, trailing `.!?,;` stripped, whitespace
collapsed) so `"hello"`, `"Hello."`, and `"HELLO !!"` all count as the
same message. Only the immediately previous message is remembered per
player; a different message in between re-arms the filter.

### Caps limit

Blocks shouty messages. Skipped when the message is shorter than
`MIN-LENGTH` (short messages like `"OK"` are always allowed). Blocks when
`upper * 100 >= letters * PERCENT`. Only letters count on both sides of
the ratio, so numbers and symbols never skew the check.

| Key | Default | Description |
| --- | --- | --- |
| `CAPS-LIMIT.MIN-LENGTH` | `8` | Below this length the check is skipped. Minimum `1`. |
| `CAPS-LIMIT.PERCENT` | `70` | Maximum uppercase-to-letter percentage before the message is blocked. `1..100`. |

### Cooldown

Minimum time in seconds between two messages from the same player.
Independent of the rate limit below: cooldown caps how often ONE message
can follow ANOTHER, the rate limit caps how many messages fit into a
rolling window. `%seconds%` in `BLOCK-MESSAGE` is the remaining wait,
rounded up.

### Message limit (rate limit)

Rolling-window rate limit: a player is allowed at most `MAX-MESSAGES`
inside the last `WINDOW-SECONDS`. `%seconds%` in `BLOCK-MESSAGE` is the
time until the oldest recorded message falls out of the window, rounded
up.

| Key | Default | Description |
| --- | --- | --- |
| `MESSAGE-LIMIT.MAX-MESSAGES` | `5` | Max messages allowed inside the window. Minimum `1`. |
| `MESSAGE-LIMIT.WINDOW-SECONDS` | `10` | Length of the sliding window in seconds. Minimum `1`. |

## Interaction with `features.chat`

If `features.chat: false` in [`config/config.yml`](../config/config.md),
no chat filters run on this backend at all. The keys in this file are
ignored until the master switch is on.

## Interaction with mutes

Chat filters run on `AsyncChatEvent` at HIGHEST priority with
`ignoreCancelled = true`. Muted messages are cancelled upstream (at the
packet layer, or by the mute event listener at LOWEST), so they never
reach the filters. A muted player therefore never counts toward the
anti-repeat, cooldown or rate-limit buffers.

## Reload

`/staffcore reload` re-reads this file and applies every value on the
next chat message. In-memory state (last message, cooldown timestamps,
rate-limit windows) is not cleared: a shortened cooldown takes effect
immediately, a raised `MAX-MESSAGES` does too, but existing buffered
timestamps are still respected.
