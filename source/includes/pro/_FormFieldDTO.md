## FormFieldDTO

```xml
<fields xmlns="http://form.modeldto.dto.proxy.platform.idamobile.com/xsd">
  <id xmlns="http://modeldto.dto.proxy.platform.idamobile.com/xsd">field_id</id>
  <comboBoxValues>
    <id xmlns="http://modeldto.dto.proxy.platform.idamobile.com/xsd">val_id</id>
    <name>40817810200005239000</name>
    <order>1</order>
    <value>40817810200005239000</value>
  </comboBoxValues>
  <comboBoxValues>
    <id xmlns="http://modeldto.dto.proxy.platform.idamobile.com/xsd">val_id</id>
    <name>40817810500005239001</name>
    <order>2</order>
    <value>40817810500005239001</value>
  </comboBoxValues>
  <defaultValue xsi:nil="true" />
  <errorMessage xsi:nil="true" />
  <fieldClass>SOURCE_ACCOUNT</fieldClass>
  <formOrder>1</formOrder>
  <groupName xsi:nil="true" />
  <hint xsi:nil="true" />
  <mandatory>true</mandatory>
  <maxLimit>0</maxLimit>
  <minLimit>0</minLimit>
  <name>Счет списания</name>
  <readOnly>false</readOnly>
  <regExp xsi:nil="true" />
</fields>
<fields xmlns="http://form.modeldto.dto.proxy.platform.idamobile.com/xsd">
  <id xmlns="http://modeldto.dto.proxy.platform.idamobile.com/xsd">field_id</id>
  <defaultValue xsi:nil="true" />
  <errorMessage xsi:nil="true" />
  <fieldClass>AMOUNT</fieldClass>
  <formOrder>1</formOrder>
  <groupName xsi:nil="true" />
  <hint xsi:nil="true" />
  <mandatory>true</mandatory>
  <maxLimit>922337203685477</maxLimit>
  <minLimit>0</minLimit>
  <name>Сумма списания</name>
  <readOnly>false</readOnly>
  <regExp xsi:nil="true" />
</fields>
```

key | type | status | comment
--- | ---- | :----: | ---:
id | string | 1..1 | идентификатор поля
name | string | 0..1 | название поля
formOrder | int | 1..1 | порядковый номер поля в форме
minLimit | int | 1..1 | в зависимости от типа поля это ограничения на значение поля формы
maxLimit | int | 1..1 | в зависимости от типа поля это ограничения на значение поля формы
regExp | string | 0..1 | регулярное выражение, которому должно соответствовать значение поля и в случае несоответствия показывается errorMessage
defaultValue | string | 0..1 | значение поля по умолчанию
mandatory | bool | 1..1 | обязательность поле формы
errorMessage | string | 0..1 | сообщение в случае, если значение поля формы не проходит валидацию
hint | string | 0..1 | отображаемая подсказка к полю
placeholder | string | 0..1 | отображаемое внутри поля
fieldClass | [FieldClass](#fieldclass) | 1..1 | тип поля формы, определяющий формат данных
comboBoxValues | [ComboBoxValueDTO](#comboboxvaluedto) | 0..1 | список значений
readOnly | bool | 0..1 | признак редактируемости

<aside class="notice">для платежных форм валюта поля AMOUNT будет привязана к валюте в выбранном счете поля SOURCE_ACCOUNT</aside>

<aside class="notice">если тип поля – SOURCE_ACCOUNT и TARGET_ACCOUNT, comboBoxValues это список пар {номер счета, идентификатор счета} для всех допустимых счетов</aside>

### FieldClass

key | type | comment
--- | ---- | ---:
SOURCE_ACCOUNT | string | список продуктов в comboBoxValues выбора 1..*
TARGET_ACCOUNT | string | список продуктов в comboBoxValues выбора 1..*
SINGLE_LINE_TEXT | string | однострочный текст
MULTI_LINE_TEXT | string | многострочный текст
CHECK_BOX | bool | чекбокс {true, false}
PASSWORD | string | однострочный текст маскированный при вводе
MONTH_YEAR | string | YYYY/MM (например 2012/11)
DATE | int | UNIXTIME (например 1394582400)
COMBO_BOX | string | список строк для comboBoxValues выбора 1..*
MONEY | int | ddddd (умноженное на 100)
PHONE | int | 99999999999
AMOUNT | int | ddddd (умноженное на 100)
PRINTED_TEXT | string | текст пояснение без возможности редактирования пользователем
PHOTO_CARD | string | ввода номера карты с элементом фотографирования карты библиотекой [card.io](http://www.card.io) и маской <code>**** **** **** ****</code>
PHOTO_QRCODE | string | информация, зашифрованную в QR-коде
IMAGE | [LogoResource](#logoresource) | картинка
HIDDEN | string | скрытое поле для технического применения
NUMERIC | int | чесло без дроби
DECIMAL | int | число с дробной частью
DYNAMIC | string | поле при вводе 2х символов делает запрос getDynamicFieldValues и в случае признака необходимости обновления текущей формы делает запрос getCurrentForm

### ComboBoxValueDTO

```xml
<comboBoxValues>
  <id xmlns="http://modeldto.dto.proxy.platform.idamobile.com/xsd">val_id</id>
  <name>Некая надпись для удобства пользователя</name>
  <order>1</order>
  <value>id_for_server</value>
</comboBoxValues>
```

key | type | status | comment
--- | ---- | :----: | ---:
id | string | 1..1 | уникальный идентификатор поля внутри системы, может быть равен value
name | string | 1..1 | string, accountNamber или cardId, отображаемая в списке
order | int | 1..1 | порядковый номер значения поля в списке
value | string | 1..1 | не уникальное значение, которое будет отправляться на Pro-сервер