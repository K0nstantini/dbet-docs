---
description: The primary contract serves as the central dispatcher, either directing incoming messages to modules or executing its own logic.
---

# Master

## Internal message handlers

### Message forwarding

Forwards the message body, along with the sender address

| From        | To                      | Input | Output                        |
|-------------|-------------------------|-------|-------------------------------|
| Any address | `Exchange`<br/>`Sender` | any   | `sender`<br/>incoming message |

### Provide the addresses of all modules

Forwards the message body, along with the module addresses

| From        | To       | Input | Output                              |
|-------------|----------|-------|-------------------------------------|
| Any address | `Sender` | any   | module address<br/>incoming message |

### Send Jettons

Transfer of Jettons to a user on request

| From     | To            | Input                            | Output                           |
|----------|---------------|----------------------------------|----------------------------------|
| Exchange | Jetton Wallet | `user_addr`<br/>`jettons_amount` | `user_addr`<br/>`jettons_amount` |

## Data

- `Jetton Wallet`
- `Exchange`

