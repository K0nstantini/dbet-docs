---
description: Purchase, sale and transfer BET tokens
---

> **First table**: sending message structure
> <br/>**Second table**: all transactions

# Buy

| To            | Op. code | Data                     |
|---------------|----------|--------------------------|
| Jetton Wallet | TODO     | `jetton_amount`<br/>TODO |

<br/>

| # | From          | To            | Operation                              |
|---|---------------|---------------|----------------------------------------|
| 1 | User Wallet   | Jetton Wallet | Send jettons to Master's Jetton Wallet |
| 2 | Jetton Wallet | Master        | Notification: Received GOVs            |
| 3 | Master        | Exchange      | Request to buy BETs                    |
| 4 | Exchange      | BET Minter    | Mint BET                               |
| 5 | BET Minter    | BET Wallet    | Fund with newly minted BETs            |

# Sell

| To     | Op. code | Data         |
|--------|----------|--------------|
| Master | TODO     | `bet_amount` |

<br/>

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

# Transfer

> Default jetton transfer process
