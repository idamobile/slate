## editForm

key | type | status | comment
--- | ---- | :----: | ---:
**Request:** | | |
form | [WsFormDTO](#wsformdto) | 1..1 | форма
**Response:** | | |
form | [WsFormDTO](#wsformdto) | 1..1 | форма
lastUpdateTime | [Date ISO 8601](https://ru.wikipedia.org/wiki/ISO_8601) | 1..1 | время последнего обновления данных
sucсess | bool | 0..1 | статус операции
errorMessage | string | 0..1 | текстовое сообщение
