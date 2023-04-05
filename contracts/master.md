---
description: The primary contract serves as the central dispatcher, either directing incoming messages to modules or executing its own logic.
---

# Master

## Internal message handler

### Message forwarding

- **From**: Any address
- **To**: Any of `Buy BET`, `Sell BET`, `Buy GOV`, `Sell GOV`, `Sender`
- **Input**: Any incoming message
- **Output**: Jettons supply and incoming message body
- **Action**: Forwards the message body, along with the jettons supply

### Provide the addresses of all modules

- **From**: Any address
- **To**: `Sender`
- **Input**: Any incoming message
- **Output**: All module addresses and incoming message body
- **Action**: Forwards the message body, along with the module addresses

___

## Data

- `Buy BET` addr
- `Sell BET` addr
- `Buy GOV` addr
- `Sell GOV` addr
- Jettons supply
