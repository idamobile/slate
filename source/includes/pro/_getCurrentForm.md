## getCurrentForm

Запрос на получение текущей формы. Принимает заполненную пользователем форму и выдаёт её с предзаполненными данными для нее

key | type | status | comment
--- | ---- | :----: | ---:
**Request:** | | |
bankClientId | string | 1..1 | идентификатор клиента
filledForm | [FilledFormDTO](#filledformdto) | 1..1 | заполненная форма с данными
**Response:** | | |
formDTO | [FormDTO](#formdto) | 1..1 | форма следующего шага
filledForm | [FilledFormDTO](#filledformdto) | 1..1 | заполненная форма с данными для formDTO
faultMessage | string | 0..1 | сообщение об ошибке
**Exception:** | | |
BankClientNotExistsException | string | 0..1 | клиент с запрошенным bankClientId не существует
