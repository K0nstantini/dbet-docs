---
description: This contract is responsible for managing the sale of Gov jettons and performs various operations related to calculating interest or managing other aspects of the sale process.
---

# Sell GOV jettons

## Internal message handler

### Primary operation for selling GOV jettons

- **From**: `Master`
- **To**: `GOV Wallet`
- **Input**:
    - `gov_wallet`
    - `gov_amount`
    - `user_addr`
    - `jettons_supply`
- **Output**:
    - `gov_amount`
    - `sell_gov`
    - `user_addr`
    - `jettons_supply`
- **Action**: Request to burn GOV jettons

### Request the total supply of BET tokens // todo

- **From**: `GOV Minter`
- **To**: `BET Minter`
- **Input**:
    - `user_addr`
    - `jettons_supply`
- **Output**: Incoming message body
- **Action**: Confirmation of successful burning of GOV and request the total supply of BET tokens

### Mint BET tokens

- **From**: `BET Minter`
- **To**: `BET Minter`
- **Input**:
    - `user_addr`
    - `jettons_supply`
    - `bet_supply`
- **Output**:
    - `user_addr`
    - `bet_amount`
- **Action**: Calc how many BETs need to for GOVs and request for minting BET tokens

___

## Data

- `Master`
- `BET Minter`
- `GOV Minter`
