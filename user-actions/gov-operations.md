---
description: Purchase, sale and transfer GOV Jettons
---

# GOV operations

{% hint style="info" %}
**First table**: sending message structure\
**Second table**: all transactions
{% endhint %}

## Buy

| To     | Op. code | Data         |
|--------|----------|--------------|
| Master | TODO     | `gov_amount` |

| # | From        | To         | Operation                           |
|---|-------------|------------|-------------------------------------|
| 1 | User Wallet | Master     | Request to buy GOVs                 |
| 2 | Master      | Exchange   | Forward message with jettons supply |
| 3 | Exchange    | BET Minter | Burn BET                            |
| 4 | BET Minter  | BET Wallet | Burn BET                            |
| 5 | BET Wallet  | BET Minter | Notification: Burned BETs           |
| 6 | BET Minter  | Exchange   | Notification: Burned BETs           |
| 7 | Exchange    | GOV Minter | Mint GOV                            |
| 8 | GOV Minter  | GOV Wallet | Fund with newly minted GOVs         |

## Sell

{% hint style="info" %}
Default jetton burning process
{% endhint %}

| To         | Op. code     | Data         |
|------------|--------------|--------------|
| GOV Wallet | `0x595f07bc` | `gov_amount` |

| # | From        | To         | Operation                   |
|---|-------------|------------|-----------------------------|
| 1 | User Wallet | GOV Wallet | Burn GOV                    |
| 2 | GOV Wallet  | GOV Minter | Notification: Burned GOVs   |
| 3 | GOV Minter  | Exchange   | Notification: Burned GOVs   |
| 4 | Exchange    | BET Minter | Mint BET                    |
| 5 | BET Minter  | BET Wallet | Fund with newly minted BETs |

## Transfer

{% hint style="info" %}
Default jetton transfer process
{% endhint %}
