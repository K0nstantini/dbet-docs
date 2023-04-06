---
description: Buy BET tokens for Jettons
---

# Buy BET

## Sending message structure

* **To**: `Jetton Wallet` contract
* **Op. code**: TODO
* **Data**:
    * `jetton_amount`
    * TODO

## All transactions

| # | From          | To            | Operation                              |
|---|---------------|---------------|----------------------------------------|
| 1 | User Wallet   | Jetton Wallet | Send jettons to Master's Jetton Wallet |
| 2 | Jetton Wallet | Master        | Notification: Received GOVs            |
| 3 | Master        | Exchange      | Request to buy BETs                    |
| 4 | Exchange      | BET Minter    | Mint BET                               |
| 5 | BET Minter    | BET Wallet    | Fund with newly minted BETs            |
