---
description: >-
  This contract is responsible for managing the purchase and sale of Gov jettons
  and BET tokens. It performs various operations related to calculating interest
  or managing other aspects of the purchase/
---

# Exchange

## Internal message handlers

### Mint GOV jettons

Confirmation of successful burning of BET tokens and request for minting GOV jettons

| From                                     | To                                       | Input                                                    | Output                                                   |
| ---------------------------------------- | ---------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| [bet-minter.md](bet-minter.md "mention") | [gov-minter.md](gov-minter.md "mention") | <p><code>user_addr</code><br><code>gov_amount</code></p> | <p><code>user_addr</code><br><code>gov_amount</code></p> |

### Mint BET tokens for GOV jettons

Confirmation of successful burning of GOV jettons, calc how many BET tokens need to for them and request for minting BET tokens

| From                                     | To                                       | Input                                                    | Output                                                   |
| ---------------------------------------- | ---------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| [gov-minter.md](gov-minter.md "mention") | [bet-minter.md](bet-minter.md "mention") | <p><code>user_addr</code><br><code>bet_amount</code></p> | <p><code>user_addr</code><br><code>bet_amount</code></p> |

### Mint BET tokens for Jettons

Confirmation of received Jettons and request for minting BET tokens

| From                             | To                                       | Input                                                       | Output                                                   |
| -------------------------------- | ---------------------------------------- | ----------------------------------------------------------- | -------------------------------------------------------- |
| [master.md](master.md "mention") | [bet-minter.md](bet-minter.md "mention") | <p><code>user_addr</code><br><code>jetton_amount</code></p> | <p><code>user_addr</code><br><code>bet_amount</code></p> |

### Burn BET tokens for Jettons

User's request to sell BET tokens for Jettons

| From                             | To                                       | Input                                                    | Output                                                   |
| -------------------------------- | ---------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| [master.md](master.md "mention") | [bet-minter.md](bet-minter.md "mention") | <p><code>user_addr</code><br><code>bet_amount</code></p> | <p><code>user_addr</code><br><code>bet_amount</code></p> |

### Burn BET tokens for GOV Jettons

Calc how many BET tokens need to for GOV jettons and request to burn BET tokens

| From                             | To                                       | Input                                                    | Output                                                                              |
| -------------------------------- | ---------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| [master.md](master.md "mention") | [bet-minter.md](bet-minter.md "mention") | <p><code>user_addr</code><br><code>gov_amount</code></p> | <p><code>user_addr</code><br><code>bet_amount</code><br><code>gov_amount</code></p> |

## Data

* `Master`
* `BET Minter`
* `GOV Minter`
* `jettons_supply`
* `bet_supply`
