## getTransactionsByDateRange

> Request:

```xml
<getTransactionsByDateRange>
    <request>
        <bankClientId>bank_client_id</bankClientId>
        <productId>product_id</productId>
        <fromIndex>0</fromIndex>
        <since>2016-08-02T13:50:00+03:00</since>
        <to>2016-08-30T13:50:00+03:00</to>
    </request>
</getTransactionsByDateRange>
```

> Response:

```xml
<getTransactionsByDateRangeResponse>
    <return>
        <balanceOnSinceDate type="AmountDTO">
            <currency>RUB</currency>
            <fxAmount>17600</fxAmount>
        </balanceOnSinceDate>
        <balanceOnToDate type="AmountDTO">
            <currency>RUB</currency>
            <fxAmount>-1054122</fxAmount>
        </balanceOnToDate>
        <lastUpdateTime>2015-08-25T21:13:08.000+03:00</lastUpdateTime>
        <transactions type="TransactionDTO">
            #
            # transaction
            #
        </transactions>
        <transactions type="TransactionDTO">
            #
            # transaction
            #
        </transactions>
    </return>
</getTransactionsByDateRangeResponse>
```

В запрос передается набор фильтров, результатом является список транзакций, отсортированный в порядке убывания даты их выполнения. Каждая из выбранных транзакций удовлетворяет каждому условию фильтра в запросе

key | type | status | comment
--- | ---- | :----: | ---:
**Request:** | | |
bankClientId | string | 1..1 | идентификатор клиента
productId | string | 1..1 | идентификатор продукта
cardId | string | 0..1 | идентификатор карты
fromIndex | int | 1..1 | начиная с какой позиции нужно передать транзакции (при первом запросе - 0)
count | int | 0..1 | максимальное количество транзакций на странице
since | [Date ISO 8601](https://ru.wikipedia.org/wiki/ISO_8601) | 1..1 | дата начала периода
to | [Date ISO 8601](https://ru.wikipedia.org/wiki/ISO_8601) | 1..1 | дата конца периода
filter | string | 0..1 | тип фильтрации для транзакций
**Response:** | | |
transactions | [TransactionDTO](#transactiondto) | 0..1 | список объектов с информацией о транзакциях
lastUpdateTime | [Date ISO 8601](https://ru.wikipedia.org/wiki/ISO_8601) | 1..1 | дата последней по времени транзакции по продукту из запрашиваемого периода
balanceOnSinceDate | [AmountDTO](#amountdto) | 0..1 | баланс на начало периода
balanceOnToDate | [AmountDTO](#amountdto) | 0..1 | баланс на конец периода
**Exception:** | | |
CardNotExistsException | string | 0..1 | карта с запрошенным cardId не существует
AccountNotExistsException | string | 0..1 | счет с запрошенным productId не существует
BankClientNotExistsException | string | 0..1 | клиент с запрошенным bankClientId не существует

<aside class="warning">lastUpdateTime используется для правильной работы с постраничным отображением списка на клиенте и представляет собой в большинстве случаев это время последней транзакции</aside>

<aside class="success">для PFM применяется с productId FINANCIAL_REPORTS</aside>
