## getBeneficiaryCategories

Запрос возвращает список категорий платежей для пользователя с идентификатором bankClientId

key | type | status | comment
--- | ---- | :----: | ---:
**Request:** | | |
bankClientId | string | 1..1 | идентификатор клиента
hash | string | 1..1 | хеш категорий, хранимых на клиенте
**Response:** | | |
beneficiaryCategories | [BeneficiaryCategoryDTO](#beneficiarycategorydto) | 0..1 | список категорий получателей, каждая категория содержит список получателей
hash | string | 0..1 | хеш текущего состояния списка
**Exception:** | | |
BankClientNotExistsException | string | 0..1 | клиент с запрошенным bankClientId не существует

<aside class="notice">В случае, если hash не равен хешу от текущего списка получателей (в частности, если hash==null), необходимо вернуть список получателей и хеш от него. В противном случае, оба компонента ответа должны быть null</aside>
