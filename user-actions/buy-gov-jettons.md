---
description: Buy GOV jettons for BET tokens
---

# Buy GOV

## Sending message structure

* **To**: `Master` contract
* **Op. code**: TODO
* **Message body**:
    * `sender`: The address of the user's wallet.
    * `buy_gov`: The address of the `Buy GOV` that can be obtained from the `Master` contract.
    * `bet_wallet`: The address of the user's `BET Wallet` contract that can be obtained from the `BET Minter` contract.
    * `amount`: The amount of GOV to buy.

## All transactions

| # | From                                            | To                                              | Operation                                                        |
|---|-------------------------------------------------|-------------------------------------------------|------------------------------------------------------------------|
| 1 | User Wallet                                     | [master.md](../contracts/master.md "mention")   | [Request to buy GOVs](../contracts/master.md#message-forwarding) |
| 2 | [master.md](../contracts/master.md "mention")   | [buy-gov.md](../contracts/buy-gov.md "mention") | Forward message with jettons supply                              |
| 3 | [buy-gov.md](../contracts/buy-gov.md "mention") | BET Minter                                      | Get total number of BETs                                         |
| 4 | BET Minter                                      | [buy-gov.md](../contracts/buy-gov.md "mention") | Provide total number of BETs                                     |
| 5 | [buy-gov.md](../contracts/buy-gov.md "mention") | BET Wallet                                      | Burn BET                                                         |
| 6 | BET Wallet                                      | BET Minter                                      | Notification: Burned BETs                                        |
| 7 | BET Minter                                      | [buy-gov.md](../contracts/buy-gov.md "mention") | Notification: Burned BETs                                        |
| 8 | [buy-gov.md](../contracts/buy-gov.md "mention") | GOV Minter                                      | Mint GOV                                                         |
| 9 | GOV Minter                                      | GOV Wallet                                      | Fund with newly minted GOVs                                      |
