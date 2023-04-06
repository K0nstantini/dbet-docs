---
description: Standard Jetton master smart-contract which is used to mint new jettons, account for circulating supply and provide common information.
---

# BET Minter

### Differences from a typical Jetton master-contract

- The burn_notification() operation notifies the owner of a successful token burning and forwards the incoming message
  body

## New internal message handlers

### Burn jettons

| From     | To         | Input                    | Output                           |
|----------|------------|--------------------------|----------------------------------|
| Exchange | BET Wallet | `user_addr`<br/>`amount` | `amount`<br/>rest of the message |


