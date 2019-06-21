## BannerDTO

key | type | status | comment
--- | ---- | :----: | ---:
id | string | 1..1 | уникальный идентификатор
order | int | 1..1 | порядок отображения
title | string | 0..1 | заголовок
text | string | 0..1 | текст
target | string | 0..1 | ссылка для перехода по клику на баннер
placement | string | 1..1 | место размещения
imageURL | string | 0..1 | адрес изображения
type | string | 0..1 | ???