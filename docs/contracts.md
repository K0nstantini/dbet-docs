## Master

Основной контракт, который перенаправляет входящие сообщения модулям или выполняет свою собственную логику.

### Functions
- Перенаправляет уведомление о поступлении средств
	- In: Jetton Wallet
	- Out: Deposit
- Перенаправляет запрос на вывод средств
	- In: User Wallet
	- Out: Withdrawal
- Подтверждает транзакции на вывод жетонов
	- In: Withdrawal
	- Out: Jetton Wallet

### Data
- **Jetton Minter**. Адрес минтера жетонов, которые мы принимаем для оплаты.
- **Jetton Wallet**. Адрес кошелька жетонов, на который мы принимаем оплату и владельцем которого является Master.
- **Deposit.**
- **Withdrawal.**

___
## Deposit

Контракт, отвечающий за логику начисления процентов или выполнения других операций, связанных с приемом депозитов.

### Functions
- Указание начислить BET токены пользователю. Здесь можно взять процент за депозит
	- In: Master
	- Out: BET Minter

### Data
- Master
- BET Minter

___
## Withdrawal

 Контракт, отвечающий за логику начисления процентов или выполнения других операций, связанных с выводом средств.
 
### Functions
- Запрос о списании/сжигании BET токенов пользователя. Здесь можно взять процент за вывод
	- In: Master
	- Out: BET Wallet
- Указание перевести жетоны пользователю
	- In: BET Minter
	- Out: Master

### Data
- Master
- BET Minter

___
## BET Minter

Управление кошельками пользователей с BET токенами.

### Functions
- Создание и пополнение кошельков пользователей
	- In: Deposit
	- Out: BET Wallet
- Уведомление об успешном списании средств с BET Wallet
	- In: BET Wallet
	- Out: Withdrawal

### Data
- Deposit
- Withdrawal
- BET supply

___
## BET Wallet

Кошелек пользователя с BET токенами.

### Functions
- Пополнение баланса кошелька
	- In: BET Minter
- Уменьшение баланса кошелька (сжигание токенов)
	- In: Withdraw
	- Out: BET Minter

### Data
- Owner
- BET Minter
- BET amount