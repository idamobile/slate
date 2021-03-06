﻿## PersonalNewsDTO

```xml
<details>
   <entry>
     <key>logo_url</key>
     <value>http://www.idamob.ru/ic.png</value>
   </entry>
   <entry>
     <key>push_description</key>
     <value>Текстовый блок с некоторым описанием</value>
   </entry>
   <entry>
     <key>name</key>
     <value>Заголовок сообщения</value>
   </entry>
   <entry>
     <key>currency</key>
     <value>100000000</value>
   </entry>
   <entry>
     <key>fxAmount</key>
     <value>RUR</value>
   </entry>
   <entry>
     <key>Период</key>
     <value>3 года</value>
   </entry>
   <entry>
     <key>Процент</key>
     <value>3%</value>
   </entry>
</details>
```

key | type | status | comment
--- | ---- | :----: | ---:
entityId | string | 1..1 | уникальный идентификатор новости
title | string | 1..1 | заголовок новости
creationDate | [Date ISO 8601](https://ru.wikipedia.org/wiki/ISO_8601) | 1..1 | дата публикации новости
preview | string | 0..1 | укороченная версия новости
isRead | bool | 0..1 | признак прочитанности
url | string | 0..1 | ссылка на новость в интернет
details | string | 0..1 | тело сообщения после открытия, функционал аналогичен ключами и структурой [pushDetails](https://doc.idamob.ru/pigeon#pushdetails)
type | string | 0..1 | тип (принимает знаечние null или MARKETING)
place | string | 0..1 | место размещения маркетингового сообщения
contentType | string | 0..1 | тип контента (TEXT или IMAGE)
content | string | 0..1 | контент (либо текст для отображения, либо ссылка на картинку)
sortOrder | int | 0..1 | порядок отображения
bgColor | string | 0..1 | цвет фона
actions | [PersonalNewsActionDTO](#personalnewsactiondto) | 0..1 | список действий

<aside class="error">используется что-то одно: либо url, либо details</aside>
