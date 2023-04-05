---
description: This contract is responsible for managing the sale of Gov jettons and performs various operations related to calculating interest or managing other aspects of the sale process.
---

# Sell GOV

## Internal message handlers

### Primary operation for selling GOV jettons

- **From**: `Master`
- **To**: `GOV Minter`
- **Input**:
    - `user_addr`
    - `jettons_supply`
    - `gov_amount`
- **Output**:
    - `user_addr`
    - `gov_amount`
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
