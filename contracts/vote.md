---
description: >-
  GOV jettons holders can vote to change the settings of a contract by locking their GOV jettons.
---

# Vote

## Internal message handlers

### Receiving votes

Receive, verify, and forward votes for validation

| From  | To              | Input                                                              | Output                                                             |
|-------|-----------------|--------------------------------------------------------------------|--------------------------------------------------------------------|
| Owner | Target contract | `amount`<br/>`user_addr`<br/>`target`<br/>`identifier`<br/>`value` | `amount`<br/>`user_addr`<br/>`target`<br/>`identifier`<br/>`value` |

### Invalid votes

The received voting data is invalid and the votes should be returned to the user

| From            | To    | Input                    | Output                   |
|-----------------|-------|--------------------------|--------------------------|
| Target contract | Owner | `amount`<br/>`user_addr` | `amount`<br/>`user_addr` |

### Approved votes

| From            | To              | Input                                                              | Output                                                             |
|-----------------|-----------------|--------------------------------------------------------------------|--------------------------------------------------------------------|
| Target contract | Votes Minter    | `amount`<br/>`user_addr`<br/>`target`<br/>`identifier`<br/>`value` | `amount`<br/>`user_addr`<br/>`target`<br/>`identifier`<br/>`value` |

## Data

- `Master`
- `Exchange`
- `voting_addr`
