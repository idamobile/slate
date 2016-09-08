## confirmTransfer

Запрос на подтверждение платежа. Должен делаться если подтверждение платежа необходимо. Использует transferCode, полученный в ходе makeTransfer

key | type | status | comment
--- | ---- | :----: | ---:
**Request:** | | |
bankClientId | string | 1..1 | идентификатор клиента
transferCode | string | 1..1 | код перевода
confirmCode | string | 1..1 | код подтверждения
**Response:** | | |
result | string | 1..1 | результат операции {OK, INVALID_CONFIRM_CODE, FAULT_MESSAGE}
message | string | 0..1 | сообщение об ошибке или иное сообщение
**Exception:** | | |
BankClientNotExistsException | string | 0..1 | клиент с запрошенным bankClientId не существует

**deprecated:**

 ||||
--- | ---- | :----: | ---:
faultMessage | string | 0..1 | сообщение об ошибке или иное сообщение