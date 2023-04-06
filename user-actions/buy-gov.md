---
description: Buy GOV jettons for BET tokens
---

# Buy GOV

## Sending message structure

* **To**: `Master` contract
* **Op. code**: TODO
* **Data**: `bet_amount`

## All transactions

| # | From        | To                                            | Operation                                                        |
|---|-------------|-----------------------------------------------|------------------------------------------------------------------|
| 1 | User Wallet | [master.md](../contracts/master.md "mention") | [Request to buy GOVs](../contracts/master.md#message-forwarding) |
| 2 | Master      | Exchange                                      | Forward message with jettons supply                              |
| 3 | Exchange    | BET Minter                                    | Burn BET                                                         |
| 4 | BET Minter  | BET Wallet                                    | Burn BET                                                         |
| 5 | BET Wallet  | BET Minter                                    | Notification: Burned BETs                                        |
| 6 | BET Minter  | Exchange                                      | Notification: Burned BETs                                        |
| 7 | Exchange    | GOV Minter                                    | Mint GOV                                                         |
| 8 | GOV Minter  | GOV Wallet                                    | Fund with newly minted GOVs                                      |
