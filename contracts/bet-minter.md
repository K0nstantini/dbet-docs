---
description: >-
  Standard Jetton master smart-contract which is used to mint new jettons,
  account for circulating supply and provide common information.
---

# BET Minter

### Differences from a typical Jetton master-contract

* The `burn_notification()` operation notifies the owner of a successful token burning and forwards the incoming message body

## New internal message handlers

### Burn jettons

| From                                 | To                                       | Input                                                | Output                                            |
| ------------------------------------ | ---------------------------------------- | ---------------------------------------------------- | ------------------------------------------------- |
| [exchange.md](exchange.md "mention") | [bet-wallet.md](bet-wallet.md "mention") | <p><code>user_addr</code><br><code>amount</code></p> | <p><code>amount</code><br>rest of the message</p> |
