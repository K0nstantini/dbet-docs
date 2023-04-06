---
description: Sell BET tokens for jettons
---

# Sell BET

## Sending message structure

* **To**: `Master` contract
* **Op. code**: TODO
* **Data**: `bet_amount`

## All transactions

| # | From        | To            | Operation                       |
|---|-------------|---------------|---------------------------------|
| 1 | User Wallet | Master        | Request to sell BETs            |
| 2 | Master      | Exchange      | Forward message                 |
| 3 | Exchange    | BET Minter    | Burn BET                        |
| 4 | BET Minter  | BET Wallet    | Burn BET                        |
| 5 | BET Wallet  | BET Minter    | Notification: Burned BETs       |
| 6 | BET Minter  | Exchange      | Notification: Burned BETs       |
| 7 | Exchange    | Master        | Request to send Jettons to user |
| 8 | Master      | Jetton Wallet | Send Jettons to user            |
