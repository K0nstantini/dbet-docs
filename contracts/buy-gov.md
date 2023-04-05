---
description: This contract is responsible for managing the purchase of Gov jettons and performs various operations related to calculating interest or managing other aspects of the purchase process.
---

# Buy GOV jettons

## Internal message handler

### Primary operation for purchasing GOV jettons

- **From**: `Master`
- **To**: `BET Minter`
- **Input**:
    - `user_addr`
    - `jettons_suply`
    - `bet_wallet`
    - `gov_amount`
- **Output**: Incoming message body
- **Action**: Request the total supply of BET tokens

### Burn BET tokens

- **From**: `BET Minter`
- **To**: `BET Wallet`
- **Input**:
    - `user_addr`
    - `jettons_suply`
    - `bet_wallet`
    - `gov_amount`
    - `bet_supply`
- **Output**:
    - `user_addr`
    - `gov_amount`
    - `bet_amount`
- **Action**: Calc how many BETs need to for GOVs and request to burn BETs

### Mint GOV jettons

- **From**: `BET Minter`
- **To**: `GOV Minter`
- **Input**:
    - `user_addr`
    - `gov_amount`
- **Output**:
    - `user_addr`
    - `gov_amount`
- **Action**: Confirmation of successful burning of BET tokens and request for minting GOV jettons

___

## Data

- `Master` addr
- `BET Minter` addr
- `GOV Minter` addr
