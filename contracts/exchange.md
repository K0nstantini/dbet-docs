---
description: >-
  This contract is responsible for managing the purchase and sale of GOV jettons
  and BET tokens. It performs various operations related to calculating interest
  or managing other aspects of the purchase.
---

# Exchange

<figure><img src="../.gitbook/assets/Exchange.excalidraw.svg" alt=""><figcaption></figcaption></figure>

## Request to check/change settings

| Field | Lenght, bits | Description                                                                                   |
| ----- | ------------ | --------------------------------------------------------------------------------------------- |
| id    | 32           | Identifier (CRC32)                                                                            |
| value | 2            | <p>0 - increment value<br>1 - decrement value<br>2 - increment step<br>3 - decrement step</p> |

