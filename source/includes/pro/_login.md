## login

Запрос проверяет корректность пары login/password, если пара верна – возвращает идентификатор клиента bankClientId, соответствующий логину на стороне бэка

key | type | status | comment
--- | ---- | :----: | ---:
**Request:** | | |
login | string | 1..1 | логин
password | string | 1..1 | пароль
validationCode | string | 0..1 | код из SMS, который передаётся только в случае ответа на команду логин с результатом VALIDATION_REQUIRED
deviceInfo | [DeviceInfoDTO](#deviceinfodto) | 1..1 | дополнительная информация об устройстве
**Response:** | | |
result | [resultLoginKey](#resultloginkey) | 1..1 | результат проверки
bankClientId | string | 1..1 | идентификатор клиента
faultMessage | string | 0..1 | расширенное сообщение об ошибке авторизации

### resultLoginKey

key | comment
--- | ---:
OK | все в порядке и можно продолжать
ERROR | показывается сообщение из faultMessage
INVALID_CREDENTIALS | не верные данные логина/пароля
PASSWORD_CHANGING_REQUIRED | необходимо обязательно сменить пароль [changePassword](#changepassword)
VALIDATION_REQUIRED | двухфакторная аутентификация с ожиданием кода из СМС
