## confirmTransfer

Запрос на подтверждение платежа. Должен делаться если подтверждение платежа необходимо. Использует transferCode, полученный в ходе makeTransfer

key | type | status | comment
--- | ---- | :----: | ---:
**Request:** | | |
bankClientId | string | 1..1 | идентификатор клиента
transferCode | string | 1..1 | код перевода
confirmCode | string | 1..1 | код подтверждения
filledForm | [FilledFormDTO](#filledformdto) | 1..1 | заполненная форма с данными
**Response:** | | |
result | [resultConfirmTransferType](#resultconfirmtransfertype) | 1..1 | результат операции
message | string | 0..1 | сообщение об ошибке или иное сообщение
**Exception:** | | |
BankClientNotExistsException | string | 0..1 | клиент с запрошенным bankClientId не существует

**deprecated:**

 ||||
--- | ---- | :----: | ---:
faultMessage | string | 0..1 | сообщение об ошибке или иное сообщение

### resultConfirmTransferType

key | comment
--- | ---:
OK | все в порядке и можно продолжать
INVALID_CONFIRM_CODE | не верные код, повторить ввод
ERROR | ошибка проверке, закрываем возможность повторить запрос
