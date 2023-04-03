# Test

| #  | From        | To         | Operation                             | Data                                                                     |
| -- | ----------- | ---------- | ------------------------------------- | ------------------------------------------------------------------------ |
| 1  | User Wallet | Master     | Query to Buy GOV                      | `user_addr, bet_minter_addr, bet_wallet_addr, gov_amount`                |
| 2  | Master      | Buy GOV    | Buy GOV Jettons                       | `user_addr, bet_minter_addr, bet_wallet_addr, gov_amount`                |
| 3  | Buy GOV     | Master     | Get total number of jettons           | `user_addr, bet_minter_addr, bet_wallet_addr, gov_amount, total_jettons` |
| 4  | Master      | Buy GOV    | Provide total number of jettons       | `user_addr, bet_minter_addr, bet_wallet_addr, gov_amount, total_jettons` |
| 5  | Buy GOV     | BET Minter | Get total number of BETs              | `user_addr, bet_wallet_addr, gov_amount, total_jettons`                  |
| 6  | BET Minter  | Buy GOV    | Provide total number of BETs          | `user_addr, bet_wallet_addr, gov_amount, total_jettons, total_bets`      |
| 7  | Buy GOV     | BET Wallet | Burn BET                              | `user_addr, buy_gov_addr, gov_amount, burn_bets`                         |
| 8  | BET Wallet  | BET Minter | Notification: burned BETs to buy GOVs | `user_addr, buy_gov_addr, gov_amount`                                    |
| 9  | BET Minter  | Buy GOV    | Notification: burned BETs to buy GOVs | `user_addr, buy_gov_addr, gov_amount`                                    |
| 10 | Buy GOV     | GOV Minter | Mint GOV                              | `user_addr, gov_amount`                                                  |
| 11 | GOV Minter  | GOV Wallet | Create and fund a wallet              | `user_addr, gov_amount`                                                  |
