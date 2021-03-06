## MarkerDTO

key | type | status | comment
--- | ---- | :----: | ---:
key | string | 1..1 | идентификатор маркера
value | string | 0..1 | информация, привязанная к маркеру

### BankClientDTO support MarkerDTO:

```xml
<tags type="MarkerDTO">
  <key>FINANCIAL_REPORTS</key>
  <value>Financial reports</value>
</tags>
```

key | type | comment
--- | --- | ---:
SPECIAL_ORDERS | string | наличие раздела в боковом меню с именем String, в который собираются формы с признаком ``PRODUCT_ORDER``
FINANCIAL_REPORTS | string | наличие в меню раздела финансовой аналитики, запрос на аналитику идет через getTransactionsByDateRange с полем id продукта ``FINANCIAL_REPORTS``
PERSONAL_NEWS | string | наличие в меню раздела персональных новостей или уведомлений о событиях

<aside class="notice">INCASSO : ``FLAG_COLLECTION``, ``FLAG_SEQUESTRATION``, ``FLAG_CALL_ANFSEQ``</aside>

### AccountDTO, CardDTO, DepositDTO, LoanDTO support MarkerDTO:

```xml
<tags type="MarkerDTO">
  <key>BUTTON_1_TEXT</key>
  <value>Payments</value>
</tags>
<tags type="MarkerDTO">
  <key>BUTTON_1_TARGET</key>
  <value>payment_short</value>
</tags>
<tags type="MarkerDTO">
  <key>BUTTON_2_TEXT</key>
  <value>Transfer by phone</value>
</tags>
<tags type="MarkerDTO">
  <key>BUTTON_2_TARGET</key>
  <value>form</value>
</tags>
```

key | type | status | comment
--- | --- | :---: | ---:
BUTTON_1_TEXT | string | 1..1 | текст подсказки на кнопке
BUTTON_1_TARGET | [TargetType](#targettype) | 1..1 | переход по нажатию кнопки
ANALYTICS | string | 0..1 | наличие на продукте кнопки перехода на экран аналитики

### TargetType

key | comment
--- | ---:
payment_full | раздел платежей полностью
payment_short | платежный раздел короткий
form | открытие формы

<aside class="notice">если необходимо более одной кнопки используется изменение порядкового номера в ключе, например ``BUTTON_2_TEXT``</aside>
<aside class="warning">TARGET является фильтром, в форме обязательно должно присутствовать поле со счетом, с которого происходит переход</aside>
