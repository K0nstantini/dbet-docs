---
description: Purchase, sale and transfer GOV Jettons.
---

# GOV operations

{% hint style="info" %}
**First table**: sending message structure\
**Second table**: sequence of transactions
{% endhint %}

## Buy

| To                                            | Op. code | Data         |
| --------------------------------------------- | -------- | ------------ |
| [master.md](../contracts/master.md "mention") | TODO     | `gov_amount` |

| # | From                                                  | To                                                    | Operation                   |
| - | ----------------------------------------------------- | ----------------------------------------------------- | --------------------------- |
| 1 | User Wallet                                           | [master.md](../contracts/master.md "mention")         | Request to buy GOVs         |
| 2 | [master.md](../contracts/master.md "mention")         | [exchange.md](../contracts/exchange.md "mention")     | Forward message             |
| 3 | [exchange.md](../contracts/exchange.md "mention")     | [bet-minter.md](../contracts/bet-minter.md "mention") | Burn BET                    |
| 4 | [bet-minter.md](../contracts/bet-minter.md "mention") | [bet-wallet.md](../contracts/bet-wallet.md "mention") | Burn BET                    |
| 5 | [bet-wallet.md](../contracts/bet-wallet.md "mention") | [bet-minter.md](../contracts/bet-minter.md "mention") | Notification: Burned BETs   |
| 6 | [bet-minter.md](../contracts/bet-minter.md "mention") | [exchange.md](../contracts/exchange.md "mention")     | Notification: Burned BETs   |
| 7 | [exchange.md](../contracts/exchange.md "mention")     | [gov-minter.md](../contracts/gov-minter.md "mention") | Mint GOV                    |
| 8 | [gov-minter.md](../contracts/gov-minter.md "mention") | [gov-wallet.md](../contracts/gov-wallet.md "mention") | Fund with newly minted GOVs |

## Sell

{% hint style="info" %}
Default jetton burning process
{% endhint %}

| To                                                    | Op. code     | Data         |
| ----------------------------------------------------- | ------------ | ------------ |
| [gov-wallet.md](../contracts/gov-wallet.md "mention") | `0x595f07bc` | `gov_amount` |

| # | From                                                  | To                                                    | Operation                   |
| - | ----------------------------------------------------- | ----------------------------------------------------- | --------------------------- |
| 1 | User Wallet                                           | [gov-wallet.md](../contracts/gov-wallet.md "mention") | Burn GOV                    |
| 2 | [gov-wallet.md](../contracts/gov-wallet.md "mention") | [gov-minter.md](../contracts/gov-minter.md "mention") | Notification: Burned GOVs   |
| 3 | [gov-minter.md](../contracts/gov-minter.md "mention") | [exchange.md](../contracts/exchange.md "mention")     | Notification: Burned GOVs   |
| 4 | [exchange.md](../contracts/exchange.md "mention")     | [bet-minter.md](../contracts/bet-minter.md "mention") | Mint BET                    |
| 5 | [bet-minter.md](../contracts/bet-minter.md "mention") | [bet-wallet.md](../contracts/bet-wallet.md "mention") | Fund with newly minted BETs |

## Transfer

{% hint style="info" %}
Default jetton transferring process
{% endhint %}
