---
description: Sell GOV jettons for BET tokens
---

# Sell GOV

## Sending message structure

* **To**: `Master` contract
* **Op. code**: TODO
* **Message body**:
    * `gov_wallet`: The address of the user's `GOV Wallet` contract that can be obtained from the `GOV Minter`
      contract. `GOV Minter` can be obtained from the `Master` contract.
    * `gov_amount`

## All transactions

| # | From        | To         | Operation                                                         |
|---|-------------|------------|-------------------------------------------------------------------|
| 1 | User Wallet | Master     | [Request to sell GOVs](../contracts/master.md#message-forwarding) |
| 2 | Master      | Sell GOV   | Forward message with jettons supply                               |
| 3 | Sell GOV    | GOV Wallet | Burn GOV                                                          |
| 4 | GOV Wallet  | GOV Minter | Notification: Burned GOVs                                         |
| 5 | GOV Minter  | Sell GOV   | Notification: Burned GOVs                                         |
| 6 | Sell GOV    | BET Minter | Get total number of BETs                                          |
| 7 | BET Minter  | Sell GOV   | Provide total number of BETs                                      |
| 8 | Sell GOV    | BET Minter | Mint BET                                                          |
| 9 | BET Minter  | BET Wallet | Fund with newly minted BETs                                       |
