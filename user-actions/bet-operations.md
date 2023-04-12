---
description: Purchase, sale and transfer BET tokens.
---

# BET operations

{% hint style="info" %}
**First table**: sending message structure\
**Second table**: sequence of transactions
{% endhint %}

## Buy

| To            | Op. code | Data                                      |
| ------------- | -------- | ----------------------------------------- |
| Jetton Wallet | TODO     | <p><code>jetton_amount</code><br>TODO</p> |



| # | From                                                  | To                                                    | Operation                              |
| - | ----------------------------------------------------- | ----------------------------------------------------- | -------------------------------------- |
| 1 | User Wallet                                           | Jetton Wallet                                         | Send jettons to Master's Jetton Wallet |
| 2 | Jetton Wallet                                         | [master.md](../contracts/master.md "mention")         | Notification: Received GOVs            |
| 3 | [master.md](../contracts/master.md "mention")         | [exchange.md](../contracts/exchange.md "mention")     | Request to buy BETs                    |
| 4 | [exchange.md](../contracts/exchange.md "mention")     | [bet-minter.md](../contracts/bet-minter.md "mention") | Mint BET                               |
| 5 | [bet-minter.md](../contracts/bet-minter.md "mention") | [bet-wallet.md](../contracts/bet-wallet.md "mention") | Fund with newly minted BETs            |

## Sell

| To                                            | Op. code | Data         |
| --------------------------------------------- | -------- | ------------ |
| [master.md](../contracts/master.md "mention") | TODO     | `bet_amount` |



| # | From                                                  | To                                                    | Operation                       |
| - | ----------------------------------------------------- | ----------------------------------------------------- | ------------------------------- |
| 1 | User Wallet                                           | [master.md](../contracts/master.md "mention")         | Request to sell BETs            |
| 2 | [master.md](../contracts/master.md "mention")         | [exchange.md](../contracts/exchange.md "mention")     | Forward message                 |
| 3 | [exchange.md](../contracts/exchange.md "mention")     | [bet-minter.md](../contracts/bet-minter.md "mention") | Burn BET                        |
| 4 | [bet-minter.md](../contracts/bet-minter.md "mention") | [bet-wallet.md](../contracts/bet-wallet.md "mention") | Burn BET                        |
| 5 | [bet-wallet.md](../contracts/bet-wallet.md "mention") | [bet-minter.md](../contracts/bet-minter.md "mention") | Notification: Burned BETs       |
| 6 | [bet-minter.md](../contracts/bet-minter.md "mention") | [exchange.md](../contracts/exchange.md "mention")     | Notification: Burned BETs       |
| 7 | [exchange.md](../contracts/exchange.md "mention")     | [master.md](../contracts/master.md "mention")         | Request to send Jettons to user |
| 8 | [master.md](../contracts/master.md "mention")         | Jetton Wallet                                         | Send Jettons to user            |

## Transfer

{% hint style="info" %}
Default jetton transferring process
{% endhint %}
