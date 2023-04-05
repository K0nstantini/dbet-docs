---
description: Standard Jetton master smart-contract which is used to mint new jettons, account for circulating supply and provide common information.
---

# GOV Minter

## Differences from a typical master-contract

- The burn_notification() operation forwards the message body to the response address, typically to notify the sender of
  a successful token burning operation. The response address can only be the `Sell GOV` contract.

## New internal message handlers

### Burn jettons

- **From**: `Sell GOV`
- **To**: `GOV Wallet`
- **Input**:
    - `user_addr`
    - `amount`
- **Output**:
    - `amount`
    - the rest of the body of the incoming message
- **Action**: Request to burn jettons

## Data

- `Buy GOV` (owner)
- `Sell GOV`
