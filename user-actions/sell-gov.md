| #  | From        | To         | Operation                       |
|----|-------------|------------|---------------------------------|
| 1  | User Wallet | Master     | Request to sell GOVs            |
| 2  | Master      | Sell GOV   | Re-send message                 |
| 3  | Sell GOV    | Master     | Get total number of jettons     |
| 4  | Master      | Sell GOV   | Provide total number of jettons |
| 5  | Sell GOV    | BET Minter | Get total number of BETs        |
| 6  | BET Minter  | Sell GOV   | Provide total number of BETs    |
| 7  | Sell GOV    | GOV Wallet | Burn GOV                        |
| 8  | GOV Wallet  | GOV Minter | Notification: Burned GOV        |
| 9  | GOV Minter  | Sell GOV   | Notification: Burned GOV        |
| 10 | Sell GOV    | BET Minter | Mint BET                        |
| 11 | BET Minter  | BET Wallet | Fund BET Wallet                 |
