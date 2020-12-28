## Документация к пакетной загрузке данных о квартирах Korter

Для осуществления пакетной выгрузки данных о квартирах, нужно предоставить URL JSON-документа, содержащего данные в следующем формате.

```
[
    {
        "id": string, (13)
        "name": string, (14)
        "blocks": [
            {
                "name": string, (2)
                "units": [
                    {
                        "area": number, (4)
                        "flat_number": string | null, (5)
                        "floor": number, (6)
                        "id": string, (7)
                        "layout_url": string, (8)
                        "price": number, (9)
                        "room_count": number, (10)
                        "status": 'sold' | 'booked' | 'available', (11)
                        "unit_type": 'flat' | 'splithouse' | 'quadrohouse' | 'cottage' | 'penthouse' | 'townhouse' | 'duplex', (12)
                    },
                    ... другие квартиры (3)
                ]
            },
            ... другие блоки (1)
        ]
    },
    ... другие ЖК
]
```

(1) Грубо говоря, блоки — это дома. Если дома разбиваются, например, на секции, то блоки — это секции в домах.
(2) Название блока. Если это просто дом, то обычно название выглядит как "Дом 1" или, например, "Блок А". Если есть, например, разбиение на секции, то название блока будет выглядеть как "Дом 1, секция 2".
(3) Квартиры тут — условное обозначение. На самом деле это просто жилая единица недвижимости. Может быть и домом.
(4) Площадь квартиры.
(5) Номер квартиры (если это квартира, а не частный дом).
(6) Номер этажа квартиры (указывается в любом случае, даже если во всем доме только один этаж).
(7) Идентификатор квартиры. Любая строка, уникальная в пределах новостройки. Не должен меняться!
(8) Ссылка на изображение планировки квартиры. Поддерживаемые форматы — png и jpg (jpeg). Размер - до 50 Мп.
(9) Цена квартиры (не цена за метр квадратный).
(10) Количество комнат в квартире.
(11) Статус продажи квартиры. Три допустимые значения: sold - продана, booked - забронирована, available - доступна для покупки.
(12) Тип недвижимости. Самый распространенный вариант - flat. Помимо него есть пентхаус и варианты для разных типов частных домов.
(13) Идентификатор новостройки. Должен быть уникален в пределах документа. Не должен меняться!
(14) Название новостройки.
