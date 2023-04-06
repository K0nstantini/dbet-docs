---
description: Sell GOV jettons for BET tokens
---

# Sell GOV

## Sending message structure

* **To**: `GOV Wallet` contract
* **Op. code**: 0x595f07bc
* **Data**: `gov_amount`

## All transactions

| # | From        | To         | Operation                    |
|---|-------------|------------|------------------------------|
| 1 | User Wallet | GOV Wallet | Burn GOV                     |
| 2 | GOV Wallet  | GOV Minter | Notification: Burned GOVs    |
| 3 | GOV Minter  | Exchange   | Notification: Burned GOVs    |
| 4 | Exchange    | BET Minter | Mint BET                     |
| 5 | BET Minter  | BET Wallet | Fund with newly minted BETs  |
