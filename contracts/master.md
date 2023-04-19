---
description: >-
  The primary contract serves as the central dispatcher, either directing
  incoming messages to modules or executing its own logic.
---

# Master

## Internal message handlers

### Message forwarding

Forwards the message body, along with the sender address

| From        | To                                                                | Input | Output                                         |
|-------------|-------------------------------------------------------------------|-------|------------------------------------------------|
| Any address | <p><a href="exchange.md">Exchange</a>,<br><code>Sender</code></p> | any   | <p><code>sender</code><br>incoming message</p> |

### Provide the addresses of all modules

Forwards the message body, along with the module addresses

| From        | To       | Input | Output                                    |
|-------------|----------|-------|-------------------------------------------|
| Any address | `Sender` | any   | <p>module address<br>incoming message</p> |

### Send Jettons

Transfer of Jettons to a user on request

| From                                 | To            | Input                                                        | Output                                                       |
|--------------------------------------|---------------|--------------------------------------------------------------|--------------------------------------------------------------|
| [exchange.md](exchange.md "mention") | Jetton Wallet | <p><code>user_addr</code><br><code>jettons_amount</code></p> | <p><code>user_addr</code><br><code>jettons_amount</code></p> |

## Data

* `Jetton Wallet`
* `Exchange`
