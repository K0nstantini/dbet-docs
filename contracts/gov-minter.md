---
description: Standard Jetton master smart-contract which is used to mint new jettons, account for circulating supply and provide common information.
---

# GOV Minter

### Differences from a typical Jetton master-contract

- The `burn_notification()` operation notifies the owner of a successful token burning

## New internal message handlers

### Jettons locking notification

| From         | To     | Input            | Output           |
|--------------|--------|------------------|------------------|
| `GOV Wallet` | `Vote` | incoming message | incoming message |

## Data

* `Vote`
