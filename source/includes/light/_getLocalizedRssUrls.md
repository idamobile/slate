## getLocalizedRssUrls

Просмотр источника новостей банка в виде RSS

key | type | status | comment
--- | ---- | :----: | ---:
**Request:** | | |
**Response:** | | |
defaultUrl | string | 1..1 | ссылка на источник по умолчанию
localizedUrls | [WsLocalizedRssUrl](#wslocalizedrssurl) | 0..1 | ссылки для источников в зависимости от локали
sucсess | bool | 0..1 | статус операции
errorMessage | string | 0..1 | текстовое сообщение
