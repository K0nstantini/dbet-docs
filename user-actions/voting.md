---
description: Voting operations for changing various parameters of smart contracts.
---

# Voting

{% hint style="info" %}
**First table**: sending message structure\
**Second table**: sequence of transactions
{% endhint %}

## Transfer GOV jettons for voting

{% hint style="info" %}
Default jetton transferring process with payload
{% endhint %}

| To              | Op. code  | Data                                                   |
|-----------------|-----------|--------------------------------------------------------|
| User GOV Wallet | 0xf8a7ea5 | `gov_amount`<br/>`target`<br/>`identifier`<br/>`value` |

- `target` - contract address to change
- `identifier` - identifier of setting to change
- `value` - new value of setting if necessary

| # | From            | To              | Operation                            |
|---|-----------------|-----------------|--------------------------------------|
| 1 | User Wallet     | User GOV Wallet | Request to transfer GOV              |
| 2 | User GOV Wallet | Vote GOV Wallet | Transfer GOV                         |
| 3 | Vote GOV Wallet | Vote            | Notification: transferred GOV        |
| 4 | Vote            | Target contract | Check request and get setting's data |

|   |                 |                 |                               |
|---|-----------------|-----------------|-------------------------------|
| 5 | Target contract | Vote            | Notification: invalid request |
| 6 | Vote            | Vote GOV Wallet | Request to return GOV to user |
| 7 | Vote GOV Wallet | User GOV Wallet | Transfer GOV back to user     |

|   |                 |                 |                                                    |
|---|-----------------|-----------------|----------------------------------------------------|
| 5 | Target contract | Vote            | Notification: valid request                        |
| 6 | Vote            | User Votes      | Store user votes                                   |
| 7 | Vote            | Target contract | If vote is successful, request to change settings. |

## Withdraw GOV jettons before consensus

| To   | Op. code | Data                                                   |
|------|----------|--------------------------------------------------------|
| Vote | TODO     | `gov_amount`<br/>`target`<br/>`identifier`<br/>`value` |

| #   | From            | To              | Operation                      |
|-----|-----------------|-----------------|--------------------------------|
| 1   | User Wallet     | Vote            | Request to withdraw GOV        |
| 2   | Vote            | GOV Minter      | Get user's GOV address         |
| 3   | GOV Minter      | Vote            | Provide user's GOV address     |
| 4   | Vote            | User Votes      | Check and subtract votes       |
| 5   | User Votes      | Vote            | Notification: Subtracted votes |
| 6.1 | Vote            | Vote GOV Wallet | Request to transfer GOV        |
| 7.1 | Vote GOV Wallet | User GOV Wallet | Transfer GOV to user           |
| 6.2 | Vote            | Vote GOV Wallet | Request to burn GOV (penalty)  |
| 7.2 | Vote GOV Wallet | GOV Minter      | Notification: Burned GOV       |
| 8.2 | GOV Minter      | Exchange        | Notification: Burned GOV       |
| 9.2 | Exchange        | Vote            | Notification: Burned GOV       |

## Withdraw GOV jettons after consensus

| To   | Op. code | Data                                  |
|------|----------|---------------------------------------|
| Vote | TODO     | `target`<br/>`identifier`<br/>`value` |

| #   | From            | To              | Operation                    |
|-----|-----------------|-----------------|------------------------------|
| 1   | User Wallet     | Vote            | Request to withdraw GOV      |
| 2   | Vote            | GOV Minter      | Get user's GOV address       |
| 3   | GOV Minter      | Vote            | Provide user's GOV address   |
| 4   | Vote            | User Votes      | Get user's votes             |
| 5   | User Votes      | Vote            | Provide user's votes         |
| 6.1 | Vote            | Vote GOV Wallet | Request to transfer GOV      |
| 7.1 | Vote GOV Wallet | User GOV Wallet | Transfer GOV to user         |
| 6.2 | Vote            | GOV Minter      | Request to mint GOV (reward) |
| 8.2 | GOV Minter      | Exchange        | Notification: Minted GOV     |
| 8.2 | Exchange        | Vote            | Notification: Minted GOV     |
