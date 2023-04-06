---
description: This contract is responsible for managing the purchase and sale of Gov jettons and BET tokens. It performs various operations related to calculating interest or managing other aspects of the purchase/selling process.
---

# Exchange

## Internal message handlers

### Mint GOV jettons

Confirmation of successful burning of BET tokens and request for minting GOV jettons

| From       | To         | Input                         | Output                        |
|------------|------------|-------------------------------|-------------------------------|
| BET Minter | GOV Minter | `user_addr` <br/>`gov_amount` | `user_addr` <br/>`gov_amount` |

### Mint BET tokens for GOV jettons

Confirmation of successful burning of GOV jettons, calc how many BET tokens need to for them and request for minting BET
tokens

| From       | To         | Input                         | Output                        |
|------------|------------|-------------------------------|-------------------------------|
| GOV Minter | BET Minter | `user_addr` <br/>`bet_amount` | `user_addr` <br/>`bet_amount` |

### Mint BET tokens for Jettons

Confirmation of received Jettons and request for minting BET tokens

| From   | To         | Input                            | Output                        |
|--------|------------|----------------------------------|-------------------------------|
| Master | BET Minter | `user_addr` <br/>`jetton_amount` | `user_addr` <br/>`bet_amount` |

### Burn BET tokens for Jettons

User's request to sell BET tokens for Jettons

| From   | To         | Input                        | Output                       |
|--------|------------|------------------------------|------------------------------|
| Master | BET Minter | `user_addr`<br/>`bet_amount` | `user_addr`<br/>`bet_amount` |

### Burn BET tokens for GOV Jettons

Calc how many BET tokens need to for GOV jettons and request to burn BET tokens

| From   | To         | Input                        | Output                                         |
|--------|------------|------------------------------|------------------------------------------------|
| Master | BET Minter | `user_addr`<br/>`gov_amount` | `user_addr` <br/>`bet_amount`<br/>`gov_amount` |

## Data

- `Master`
- `BET Minter`
- `GOV Minter`
- `jettons_supply`
- `bet_supply`
