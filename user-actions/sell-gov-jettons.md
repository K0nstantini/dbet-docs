---
description: Sell GOV jettons for BET tokens
---

# Sell GOV

## Sending message structure

* **To**: `Master` contract
* **Op. code**: TODO
* **Message body**:
    * `Sender`: The address of the user's wallet.
    * `Sell GOV`: The address of the contract that can be obtained from the Master contract.
    * `Amount`: The amount of GOV to sell.

## All transactions

| # | From                                          | To                                            | Operation                                                         |
|---|-----------------------------------------------|-----------------------------------------------|-------------------------------------------------------------------|
| 1 | User Wallet                                   | [master.md](../contracts/master.md "mention") | [Request to sell GOVs](../contracts/master.md#message-forwarding) |
| 2 | [master.md](../contracts/master.md "mention") | Sell GOV                                      | Forward message with jettons supply                               |
| 3 | Sell GOV                                      | BET Minter                                    | Get total number of BETs                                          |
| 4 | BET Minter                                    | Sell GOV                                      | Provide total number of BETs                                      |
| 5 | Sell GOV                                      | GOV Wallet                                    | Burn GOV                                                          |
| 6 | GOV Wallet                                    | GOV Minter                                    | Notification: Burned GOVs                                         |
| 7 | GOV Minter                                    | Sell GOV                                      | Notification: Burned GOVs                                         |
| 8 | Sell GOV                                      | BET Minter                                    | Mint BET                                                          |
| 9 | BET Minter                                    | BET Wallet                                    | Fund with newly minted BETs                                       |
