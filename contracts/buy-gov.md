---
description: This contract is responsible for managing the purchase of Gov jettons and performs various operations related to calculating interest or managing other aspects of the purchase process.
---

# Buy GOV jettons

## Internal message handler

### Primary operation for purchasing GOV jettons

- **From**: `Master`
- **To**: `BET Minter`
- **Input**:
    - `bet_wallet`
    - `gov_amount`
    - `user_addr`
    - `jettons_supply`
- **Output**: Incoming message body
- **Action**: Request the total supply of BET tokens

### Burn BET tokens

- **From**: `BET Minter`
- **To**: `BET Wallet`
- **Input**:
    - `bet_wallet`
    - `gov_amount`
    - `user_addr`
    - `jettons_supply`
    - `bet_supply`
- **Output**:
    - `bet_amount`
    - `buy_gov`
    - `user_addr`
    - `gov_amount`
- **Action**: Calc how many BETs need to for GOVs and request to burn BET tokens

### Mint GOV jettons

- **From**: `BET Minter`
- **To**: `GOV Minter`
- **Input**:
    - `user_addr`
    - `gov_amount`
- **Output**: Incoming message body
- **Action**: Confirmation of successful burning of BET tokens and request for minting GOV jettons

___

## Data

- `Master`
- `BET Minter`
- `GOV Minter`
