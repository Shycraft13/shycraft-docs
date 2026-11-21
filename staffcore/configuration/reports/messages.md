# `reports/messages.yml`

Location: `plugins/StaffCore/reports/messages.yml`

Strings shown by `/report` and `/reports`. One-line messages go to chat and the
action bar, see
[Chat and action bar messages](../config/config.md#chat-and-action-bar-messages);
longer staff-facing output goes to chat only.

```yaml
no-permission:            "&cNo permission."
player-not-found:         "&cPlayer not found."
cannot-report-self:       "&cYou cannot report yourself."
cannot-report-staff:      "&cThis player cannot be reported."
cooldown-active:          "&cYou can send another report in %time%."
message-too-short:        "&cYour report must be at least %min% characters."
no-reports-found:         "&cNo reports found."
report-failed:            "&cYour report could not be saved. Please try again."
status-failed:            "&cCould not update the report."

report-submitted:         "&#AAAA00&lREPORT &r&7» &fThanks, your report on &#00FC99%target%&f has been filed."
report-dismissed:         "&#AAAA00&lREPORT &r&7» &fDismissed report &#FCE300#%id%&f."
report-reviewed:          "&#AAAA00&lREPORT &r&7» &fMarked report &#FCE300#%id%&f as reviewed."
report-reopened:          "&#AAAA00&lREPORT &r&7» &fSet report &#FCE300#%id% &fback to new."
```
