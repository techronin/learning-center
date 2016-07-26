## Урок 12: Проведение crowdsale

> Уровень сложности урока: высокий.

**Создаваемые на данном уроке модули ДАО:**

- `Crowdsale`

**Используемые для взаимодействия в данном уроке модули ДАО:**

- `TokenEmission`. Контракт, хранящий реестр токенов внутренней валюты ДАО `DAO credit`.
- `Crowdsale`. Контракт, с помощью которого организуется распродажа токенов `DAO credit`.

### Описание урока

Помните, самая важная задача организации − повышать ликвидность своей внутренней валюты, насыщая рынок ДАО предложениями. Для стимулирования рынка необходимо инвестировать в поставщиков ценностей рынка ДАО, а для этого необходимы существенные финансовые средства. Для того, чтобы привлечь дополнительные капиталы давайте выполним эмиссию и продажу по фиксированной цене внутренней валюты организации − crowdsale.

**Для того, чтобы выполнить crowdsale необходимо:**

- Обратиться к `DAO factory` и найти контракт сборщика с названием `Crowdsale builder`, при обращении к данному сборщику необходимо указать адрес реестра, хранящего токены `DAO credit`, а также адрес реестра, хранящего капитал организации в эфирах `Ether funds`.

Для увеличения количества токенов `DAO credit` за счёт привлечения финансирования необходимо воспользоваться сборщиком [BuilderCrowdsale](https://github.com/airalab/core/wiki/API-Reference#buildercrowdsale), который создаст модуль инфраструктуры ДАО [Crowdsale](https://github.com/airalab/core/wiki/API-Reference#crowdsale).

**Параметры, которые необходимо задать при обращении к сборщику `Crowdsale`:**

- Адрес контракта `Cashflow` для перевода на него средств при успешном завершении
- Адрес токена `DAO credit`
- Время старта Crowdsale (UNIX-время)
- Период проведения Crowdsale в секундах
- Начальная стоимость токена `DAO credit`
- Шаг увеличения стоимости в процентах
- Период шага увеличения стоимости в секундах
- Минимальную сумму привлекаемых средств
- Максимальную сумму привлекаемых средств

> в данном уроке максимальную сумму привлекаемых средств необходимо указать равной 5 эфиров.

> После создания контракта на его адрес необходимо перевести число токенов `DAO credit` для продажи.

## Проверка умений

> Успешное выполнение урока в официальной сети даст: 200 `air`

Для успешного прохождения урока необходимо внести 5 эфиров с любого аккаунта, который в дальнейшем станет владельцем новых токенов `DAO credit`. Чтобы закончить урок необходимо отправить транзакцию после наполнения Crowdsale 5 эфирами на `Lesson 12` вызвав функцию `Execute()`.