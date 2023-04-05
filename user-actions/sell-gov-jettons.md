---
description: Sell GOV jettons for BET tokens
---

# Sell GOV

## Sending message structure

* **To**: `Master` contract
* **Op. code**: TODO
* **Message body**: `gov_amount`

## All transactions

| #  | From                                              | To                                                | Operation                                                         |
|----|---------------------------------------------------|---------------------------------------------------|-------------------------------------------------------------------|
| 1  | User Wallet                                       | [master.md](../contracts/master.md "mention")     | [Request to sell GOVs](../contracts/master.md#message-forwarding) |
| 2  | [master.md](../contracts/master.md "mention")     | [sell-gov.md](../contracts/sell-gov.md "mention") | Forward message with jettons supply                               |
| 3  | [sell-gov.md](../contracts/sell-gov.md "mention") | GOV Minter                                        | Burn GOV                                                          |
| 4  | GOV Minter                                        | GOV Wallet                                        | Burn GOV                                                          |
| 5  | GOV Wallet                                        | GOV Minter                                        | Notification: Burned GOVs                                         |
| 6  | GOV Minter                                        | [sell-gov.md](../contracts/sell-gov.md "mention") | Notification: Burned GOVs                                         |
| 7  | Sell GOV                                          | BET Minter                                        | Get total number of BETs                                          |
| 8  | BET Minter                                        | [sell-gov.md](../contracts/sell-gov.md "mention") | Provide total number of BETs                                      |
| 9  | [sell-gov.md](../contracts/sell-gov.md "mention") | BET Minter                                        | Mint BET                                                          |
| 10 | BET Minter                                        | BET Wallet                                        | Fund with newly minted BETs                                       |
