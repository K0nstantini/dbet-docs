---
description: Voting operations for changing various parameters of smart contracts.
---

# Voting

{% hint style="info" %}
**First table**: sending message structure\
**Second table**: sequence of transactions
{% endhint %}

## Transfer GOV jettons for voting

{% hint style="info" %}
Default jetton transferring process with payload
{% endhint %}

| To              | Op. code  | Data                                                                                                   |
|-----------------|-----------|--------------------------------------------------------------------------------------------------------|
| User GOV Wallet | 0xf8a7ea5 | <p><code>gov_amount</code><br><code>target</code><br><code>identifier</code><br><code>value</code></p> |

* `target` - contract address to change
* `identifier` - identifier of setting to change
* `value` - new value of setting if necessary

| # | From                                                       | To                                                         | Operation                            |
|---|------------------------------------------------------------|------------------------------------------------------------|--------------------------------------|
| 1 | User Wallet                                                | User [gov-wallet.md](../contracts/gov-wallet.md "mention") | Request to transfer GOV              |
| 2 | User [gov-wallet.md](../contracts/gov-wallet.md "mention") | Vote [gov-wallet.md](../contracts/gov-wallet.md "mention") | Transfer GOV                         |
| 3 | Vote [gov-wallet.md](../contracts/gov-wallet.md "mention") | Owner                                                      | Notification: transferred GOV        |
| 4 | Owner                                                      | [vote.md](../contracts/vote.md "mention")                  | Notification: transferred GOV        |
| 5 | [vote.md](../contracts/vote.md "mention")                  | Target contract                                            | Check request and get setting's data |

| # | From                                                       | To                                                         | Operation                     |
|---|------------------------------------------------------------|------------------------------------------------------------|-------------------------------|
| 6 | Target contract                                            | [vote.md](../contracts/vote.md "mention")                  | Notification: invalid request |
| 7 | [vote.md](../contracts/vote.md "mention")                  | Owner                                                      | Request to return GOV to user |
| 8 | Owner                                                      | Vote [gov-wallet.md](../contracts/gov-wallet.md "mention") | Request to transfer GOV       |
| 9 | Vote [gov-wallet.md](../contracts/gov-wallet.md "mention") | User [gov-wallet.md](../contracts/gov-wallet.md "mention") | Transfer GOV                  |

| #   | From                                      | To                                        | Operation                                          |
|-----|-------------------------------------------|-------------------------------------------|----------------------------------------------------|
| 6   | Target contract                           | [vote.md](../contracts/vote.md "mention") | Notification: approved votes                       |
| 7.1 | [vote.md](../contracts/vote.md "mention") | Votes Minter                              | Request to store user votes                        |
| 8   | Votes Minter                              | User Votes                                | Store user votes                                   |
| 7.2 | [vote.md](../contracts/vote.md "mention") | Target contract                           | If vote is successful, request to change settings. |

## Withdraw GOV jettons before consensus

| To   | Op. code | Data                                                                                                   |
|------|----------|--------------------------------------------------------------------------------------------------------|
| Vote | TODO     | <p><code>gov_amount</code><br><code>target</code><br><code>identifier</code><br><code>value</code></p> |

| #   | From                                                       | To                                                         | Operation                      |
|-----|------------------------------------------------------------|------------------------------------------------------------|--------------------------------|
| 1   | User Wallet                                                | [vote.md](../contracts/vote.md "mention")                  | Request to withdraw GOV        |
| 2   | [vote.md](../contracts/vote.md "mention")                  | [gov-minter.md](../contracts/gov-minter.md "mention")      | Get user's GOV address         |
| 3   | [gov-minter.md](../contracts/gov-minter.md "mention")      | [vote.md](../contracts/vote.md "mention")                  | Provide user's GOV address     |
| 4   | [vote.md](../contracts/vote.md "mention")                  | User Votes                                                 | Check and subtract votes       |
| 5   | User Votes                                                 | [vote.md](../contracts/vote.md "mention")                  | Notification: Subtracted votes |
| 6.1 | [vote.md](../contracts/vote.md "mention")                  | Vote [gov-wallet.md](../contracts/gov-wallet.md "mention") | Request to transfer GOV        |
| 7.1 | Vote [gov-wallet.md](../contracts/gov-wallet.md "mention") | User [gov-wallet.md](../contracts/gov-wallet.md "mention") | Transfer GOV to user           |
| 6.2 | [vote.md](../contracts/vote.md "mention")                  | Vote [gov-wallet.md](../contracts/gov-wallet.md "mention") | Request to burn GOV (penalty)  |
| 7.2 | Vote [gov-wallet.md](../contracts/gov-wallet.md "mention") | [gov-minter.md](../contracts/gov-minter.md "mention")      | Notification: Burned GOV       |
| 8.2 | [gov-minter.md](../contracts/gov-minter.md "mention")      | [exchange.md](../contracts/exchange.md "mention")          | Notification: Burned GOV       |
| 9.2 | [exchange.md](../contracts/exchange.md "mention")          | [vote.md](../contracts/vote.md "mention")                  | Notification: Burned GOV       |

## Withdraw GOV jettons after consensus

| To                                        | Op. code | Data                                                                        |
|-------------------------------------------|----------|-----------------------------------------------------------------------------|
| [vote.md](../contracts/vote.md "mention") | TODO     | <p><code>target</code><br><code>identifier</code><br><code>value</code></p> |

| #   | From                                                       | To                                                         | Operation                    |
|-----|------------------------------------------------------------|------------------------------------------------------------|------------------------------|
| 1   | User Wallet                                                | [vote.md](../contracts/vote.md "mention")                  | Request to withdraw GOV      |
| 2   | [vote.md](../contracts/vote.md "mention")                  | [gov-minter.md](../contracts/gov-minter.md "mention")      | Get user's GOV address       |
| 3   | [gov-minter.md](../contracts/gov-minter.md "mention")      | [vote.md](../contracts/vote.md "mention")                  | Provide user's GOV address   |
| 4   | [vote.md](../contracts/vote.md "mention")                  | User Votes                                                 | Get user's votes             |
| 5   | User Votes                                                 | [vote.md](../contracts/vote.md "mention")                  | Provide user's votes         |
| 6.1 | [vote.md](../contracts/vote.md "mention")                  | Vote [gov-wallet.md](../contracts/gov-wallet.md "mention") | Request to transfer GOV      |
| 7.1 | Vote [gov-wallet.md](../contracts/gov-wallet.md "mention") | User [gov-wallet.md](../contracts/gov-wallet.md "mention") | Transfer GOV to user         |
| 6.2 | [vote.md](../contracts/vote.md "mention")                  | [exchange.md](../contracts/exchange.md "mention")          | Request to mint GOV (reward) |
| 8.2 | [exchange.md](../contracts/exchange.md "mention")          | [gov-minter.md](../contracts/gov-minter.md "mention")      | Request to mint GOV          |
| 8.2 | [gov-minter.md](../contracts/gov-minter.md "mention")      | User [gov-wallet.md](../contracts/gov-wallet.md "mention") | Transfer GOV to user         |

