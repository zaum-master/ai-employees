# Integration routing

Use the buyer's description of where work happens to choose integrations. Do
not make them select a technical integration before you understand their work.

| Buyer describes work in | Setup action | Initial boundary |
| --- | --- | --- |
| WhatsApp | Pair the buyer's account, then bind the Program Manager to the buyer's self-chat | The buyer is the only allowlisted contact; do not read or message others |
| Telegram | Create or connect the dedicated control conversation and verify one two-way exchange | Treat it as the buyer's control channel |
| Slack | Set up the dedicated app/bot, request only the scopes needed, and add it only to named work channels | Require a mention until the buyer intentionally changes that policy |
| Email | Connect the stated mailbox or use the configured email surface | Drafts only at first; do not send external mail |
| Another Hermes-supported surface | Inspect the current Hermes documentation, then connect the smallest scope that supports the described work | Verify the connection before relying on it; do not assume a capability or credential exists |
| Jira, Linear, Asana, ClickUp, spreadsheet | Do not configure during initial setup | Keep the local task record as the source of truth in v1 |
| More than one surface | Connect the surface with the clearest first project first, then continue with the rest | Verify one surface at a time |
| No preference or uncertainty | Recommend WhatsApp self-chat first, then Telegram | Give the buyer a working conversation before adding organization access |

For a connection that needs an account owner to complete a login, QR scan,
workspace approval, or token creation, explain the immediate next action in
plain language and resume as soon as it is complete. Do not invent scopes,
tokens, channel IDs, phone numbers, or successful connection status.
