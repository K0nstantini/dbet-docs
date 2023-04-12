---
description: Standard Jetton wallet smart-contract.
---

# GOV Wallet

## New internal message handlers

### Jettons locking for voting

| From        | To           | Input                                                           | Output           |
|-------------|--------------|-----------------------------------------------------------------|------------------|
| User Wallet | `GOV Minter` | `amount`<br/>`contract`<br/>`identifier`<br/>`value`<br/>`vote` | incoming message |
