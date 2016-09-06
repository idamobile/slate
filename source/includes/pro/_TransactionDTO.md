## TransactionDTO

key | type | status | comment
--- | ---- | :----: | ---:
id | string | 1..1 | идентификатор операции
name | string | 0..1 | наименование операции
transactionAmount | [AmountDTO](#amountdto) | 1..1 | сумма в валюте операции
billingAmount | [AmountDTO](#amountdto) | 1..1 | сумма в валюте счета
postDate | [Date ISO 8601](https://ru.wikipedia.org/wiki/ISO_8601) | 1..1 | дата создания заявки на проведение операции
executionDate | [Date ISO 8601](https://ru.wikipedia.org/wiki/ISO_8601) | 0..1 | дата исполнения операции
description | string | 0..1 | детали операции
status | [TransactionStatus](#transactionstatus) | 1..1 | текущий статус транзакции
isOutgoing | bool | 0..1 | операция переводит деньги СО счета
filledFormId | string | 0..1 | идентификатор соответствующей заполненной формы
tags | [MarkerDTO](#markerdto) | 0..1 | дополнительные поля
isAuthorization | bool | 0..1 | операция авторизации
cardId | string | 0..1 | ID карты, с которой связана данная транзакция
sic | int | 0..1 | mcc код из процессинга или из SmartTransaction для PFM

### TransactionStatus

key | comment
--- | ---:
POSTED | 
ACCEPTED | 
HOLD | 
REJECTED | 
COMPLETE | 