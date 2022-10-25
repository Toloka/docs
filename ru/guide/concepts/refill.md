# {% if locale == "en-com" %}Пополнение счета{% endif %}{% if locale == "ru-ru" %}Для нерезидентов России{% endif %}

{% if locale == "ru-ru" %}Нерезиденты России могут пополнять счет в Толоке в долларах США. Минимальная сумма пополнения — 1 доллар.{% endif %}

## Способы пополнения {#method}

Пополнить счет в Толоке можно одним из способов:

#### Банковская карта Visa или EuroCard/MasterCard

Платеж зачисляется в течение 15 минут.

Если при [регистрации](access.md) в Толоке вы выбрали {% if locale == "ru-ru" %}**Тип профиля → Юридическое лицо**{% endif %}{% if locale == "en-com" %}**Profile type → Legal entity**{% endif %}, то банковская карта должна быть корпоративной.

{% cut "Список стран, в которых доступен перевод банковской картой" %}

{% if locale == "ru-ru" %}

- Россия
- Украина
- Беларусь
- Казахстан
- Узбекистан
- Турция
- Австрия
- Азербайджан
- Аландские острова
- Албания
- Андорра
- Армения
- Бельгия
- Болгария
- Босния и Герцеговина
- Ватикан
- Великобритания
- Венгрия
- Вьетнам
- Германия
- Гернси
- Гибралтар
- Гонконг
- Греция
- Грузия
- Дания
- Джерси
- Израиль
- Ирландия
- Исландия
- Испания
- Италия
- Канада
- Кипр
- Киргизия
- Китай
- Латвия
- Литва
- Лихтенштейн
- Люксембург
- Македония
- Малайзия
- Мальта
- Молдова
- Монако
- Нидерланды
- Норвегия
- Объединенные Арабские Эмираты
- Остров Мэн
- Польша
- Португалия
- Румыния
- Сан-Марино
- Сербия
- Словакия
- Словения
- Соединенные Штаты Америки
- Таджикистан
- Таиланд
- Тайвань
- Туркмения
- Фарерские острова
- Финляндия
- Франция
- Хорватия
- Черногория
- Чешская Республика
- Швейцария
- Швеция
- Шпицберген и Ян-Майен
- Эстония
- Южная Корея

{% endif %}{% if locale == "en-com" %}

- Russia
- Ukraine
- Belarus
- Kazakhstan
- Uzbekistan
- Turkey
- Åland Islands
- Albania
- Andorra
- Armenia
- Austria
- Azerbaijan
- Belgium
- Bosnia and Herzegovina
- Bulgaria
- Canada
- China
- Croatia
- Cyprus
- Czech Republic
- Denmark
- Estonia
- Faroe Islands
- Finland
- France
- Georgia
- Germany
- Gibraltar
- Greece
- Guernsey
- Hong Kong
- Hungary
- Iceland
- Ireland
- Isle of Man
- Israel
- Italy
- Jersey
- Kyrgyzstan
- Latvia
- Liechtenstein
- Lithuania
- Luxembourg
- Macedonia
- Malaysia
- Malta
- Moldova
- Monaco
- Montenegro
- Netherlands
- Norway
- Poland
- Portugal
- Romania
- San Marino
- Serbia
- Slovakia
- Slovenia
- South Korea
- Spain
- Svalbard and Jan Mayen
- Sweden
- Switzerland
- Taiwan
- Tajikistan
- Thailand
- Turkmenistan
- United Arab Emirates
- United Kingdom
- USA
- Vatican City State
- Vietnam

{% endif %}

{% endcut %}

#### Банковский перевод

Срок зачисления денег — от 3 до 10 дней.

При совершении перевода в назначении платежа укажите номер выставленного счета.

#### Перевод через PayPal

Платеж зачисляется в течение 15 минут.

Для совершения платежа вы будете перенаправлены на сайт [PayPal]({{ paypal }}).

{% note alert "Ограничение" %}

Для резидентов Швейцарии перевод через PayPal недоступен.

{% endnote %}

{% cut "Регионы, в которых невозможен PayPal-перевод" %}

- Крым
- Украина
- Узбекистан
- Турция
- Иран
- Куба
- Судан
- Сирия
- Северная Корея

{% endcut %}

Полный список опубликован на [сайте Министерства финансов США](https://www.treasury.gov/resource-center/sanctions/Programs/Pages/Programs.aspx).

## Пошаговая инструкция {#step-by-step}

1. На странице [Профиль]({{ profile }}) нажмите кнопку {% if locale == "ru-ru" %}**Пополнить счет**{% endif %}{% if locale == "en-com" %}**Top up account**{% endif %}.

1. Если вы пополняете счет первый раз, то откроется страница {% if locale == "ru-ru" %}**Подключение к биллинговой системе**{% endif %}{% if locale == "en-com" %}**Connect to billing system**{% endif %}. Выполните следующие шаги:

    1. Заполните ваши данные.

        {% note info %}

        Эти данные будут включены в отчетные документы (акты о выполненных услугах).

        {% endnote %}

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Подключиться**{% endif %}{% if locale == "en-com" %}**Connect**{% endif %}.

1. Введите сумму перевода.

    Минимальная сумма пополнения — 1 доллар.

    Максимальная сумма пополнения с банковской карты — 3500 долларов.

1. Выберите способ оплаты: {% if locale == "ru-ru" %}**Банковской картой**{% endif %}{% if locale == "en-com" %}**Bank card**{% endif %} или {% if locale == "ru-ru" %}**Банковский перевод или Paypal**{% endif %}{% if locale == "en-com" %}**Bank transfer or Paypal**{% endif %}.

1. Нажмите кнопку {% if locale == "ru-ru" %}**Пополнить**{% endif %}{% if locale == "en-com" %}**Top up**{% endif %}.

    {% list tabs %}

    - Карта

      1. Введите данные вашей карты.

          {% note info %}

          Чтобы каждый раз не вводить данные карты, включите опцию {% if locale == "ru-ru" %}**Запомнить карту для следующих заказов**{% endif %}{% if locale == "en-com" %}**Save card for future payments**{% endif %}.

          {% endnote %}

      1. Нажмите кнопку {% if locale == "ru-ru" %}**Оплатить**{% endif %}{% if locale == "en-com" %}**Pay**{% endif %}.

      1. Отслеживайте поступление денег на счет в Толоке на странице [Профиль]({{ profile }}) (вкладка {% if locale == "ru-ru" %}**История поступлений**{% endif %}{% if locale == "en-com" %}**Transactions history**{% endif %}).

    - Банковский счет/PayPal

      1. Вы будете перенаправлены в сервис [Яндекс Баланс]({{ balance }}).

      1. Выберите плательщика (физическое или юридическое лицо) и подходящий способ оплаты.

      1. Прикрепите документы:

          - Для физических лиц

            - копию первой страницы паспорта;

          - Для юридических лиц

            - свидетельство о регистрации юридического лица;

            - карточка предприятия с реквизитами и контактной информацией.

      1. Нажмите кнопку {% if locale == "ru-ru" %}**Выбрать**{% endif %}{% if locale == "en-com" %}**Select**{% endif %}.

      1. Проверьте введенные данные.

      Чтобы вернуться к выбору способа оплаты и изменению данных плательщика, нажмите {% if locale == "ru-ru" %}**Изменить способ оплаты или плательщика**{% endif %}{% if locale == "en-com" %}**Change payer or payment method**{% endif %}.

      1. Нажмите кнопку {% if locale == "ru-ru" %}**Выставить счет**{% endif %}{% if locale == "en-com" %}**Create a billing invoice**{% endif %}.

          Если вы выбрали {% if locale == "ru-ru" %}**Способ оплаты → Банк для физических лиц, доллары (нерезиденты, Швейцария)**{% endif %}{% if locale == "en-com" %}**Payment method → Bank deposit in US dollars for non-resident individuals (Switzerland)**{% endif %}, получите счет с реквизитами для оплаты.

      1. Нажмите кнопку {% if locale == "ru-ru" %}**Оплатить**{% endif %}{% if locale == "en-com" %}**Pay**{% endif %}.

          Если вы выбрали {% if locale == "ru-ru" %}**Способ оплаты → PayPal**{% endif %}{% if locale == "en-com" %}**Payment method → PayPal**{% endif %}, вы будете перенаправлены на сайт платежной системы для совершения платежа.

          Если вы выбрали {% if locale == "ru-ru" %}**Способ оплаты → Банковская карта (для нерезидентов Швейцарии) – доллары**{% endif %}{% if locale == "en-com" %}**Payment method → Banking card in dollars – non residents Switzerland) – US dollars**{% endif %}, введите данные банковской карты и завершите платеж. Деньги будут сконвертированы по курсу вашего банка, если валюта карты не доллары.

          {% note info %}

          Если вы используете кошелек в сервисе ЮMoney, то при переходе к оплате у вас могут запросить [платежный пароль](https://yandex.ru/support/money/password/permanent.html).

          {% endnote %}

      1. Отслеживайте поступление денег на счет:

          - В Толоке на странице [Профиль]({{ profile }}) (вкладка {% if locale == "ru-ru" %}**История поступлений**{% endif %}{% if locale == "en-com" %}**Transactions history**{% endif %}).

          - В Яндекс Балансе на странице [Счета]({{ invoices }}).

    {% endlist %}

## Что дальше {#what_next}

- [Запустите пул](pool-run-and-stop.md).

## Решение проблем {#troubleshooting}

[Получить закрывающие документы и акты](../troubleshooting/support.md#feedback_g3b_vj3_qjb)

[Вернуть средства, перечисленные на счет в Толоку](../troubleshooting/support.md#feedback_khw_wc3_qjb)

Если деньги не поступили на счет в течение указанного срока:

{% include [contact-support](../_includes/contact-support-help.md) %}