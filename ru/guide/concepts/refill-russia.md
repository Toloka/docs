# Для резидентов России

{% include [deprecate](../../_includes/deprecate.md) %}

Резиденты России могут пополнять счет в Толоке только в рублях, но сумма пополнения указывается в долларах США. Затем она будет рассчитана в рублях с учетом НДС. Конверсия «доллар—рубль» будет произведена по [курсу Центрального банка России](notes.md#bank) на момент выставления счета по [всемирному времени (UTC)](notes.md#utc).

{% note alert "Ограничение" %}

Минимальная сумма пополнения — 1 доллар.

{% endnote %}

## Способы пополнения {#section_wkq_rsp_qjb}

В зависимости от того, какой **Тип профиля** вы выбрали при [регистрации](access.md) — физическое или юридическое лицо — вам доступны разные способы пополнения счета:

#|
|| | **Способ пополнения счета** | **Срок зачисления платежа** | **Информация для поля Назначение платежа** ||
|| Физическое лицо | Банковская карта Visa или EuroCard/MasterCard | 15 минут | ||
|| Физическое лицо | Банковский перевод | от 3 до 10 дней | Номер выставленного счета ||
|| Юридическое лицо | **Корпоративная** банковская карта Visa или EuroCard/MasterCard | 15 минут | ||
|| Юридическое лицо | Банковский перевод | от 3 до 10 дней | Номер выставленного счета ||
|#

## Пошаговая инструкция {#step-by-step}

1. На странице [Профиль]({{ profile }}) нажмите кнопку **Пополнить счет**.

1. Если вы пополняете счет первый раз, то откроется страница **Подключение к биллинговой системе**. Выполните следующие шаги:

    1. Заполните ваши данные.

        {% note info %}

        Эти данные будут включены в отчетные документы (акты о выполненных услугах).

        {% endnote %}

    1. Нажмите кнопку **Подключиться**.

1. Введите сумму перевода.

    Минимальная сумма пополнения — 1 доллар.

    Максимальная сумма пополнения с банковской карты — 3500 долларов.

1. Выберите способ оплаты: **Банковской картой** или **Банковский перевод или Paypal**.

1. Нажмите кнопку **Пополнить**.

    {% list tabs %}

    - Карта

      1. Введите данные вашей карты.

          {% note info %}

          Чтобы каждый раз не вводить данные карты, включите опцию **Запомнить карту для следующих заказов**.

          {% endnote %}

      1. Нажмите кнопку **Оплатить**.

      1. Отслеживайте поступление денег на счет в Толоке на странице [Профиль]({{ profile }}) (вкладка **История поступлений**).

    - Банковский счет/PayPal

      1. Вы будете перенаправлены в сервис [Яндекс Баланс]({{ balance }}).

      1. Выберите плательщика (физическое или юридическое лицо) и подходящий способ оплаты.

      1. Прикрепите документы:

          - Для физических лиц

              - копию первой страницы паспорта;

          - Для юридических лиц

              - свидетельство о регистрации юридического лица;

              - карточка предприятия с реквизитами и контактной информацией.

      1. Нажмите кнопку **Выбрать**.

      1. Проверьте введенные данные.

          Чтобы вернуться к выбору способа оплаты и изменению данных плательщика, нажмите **Изменить способ оплаты или плательщика**.

      1. Нажмите кнопку **Выставить счет**.

          Если вы выбрали , получите счет с реквизитами для оплаты.

      1. Нажмите кнопку **Оплатить**.

          Если вы выбрали , вы будете перенаправлены на сайт платежной системы для совершения платежа.

          Если вы выбрали , введите данные банковской карты и завершите платеж. Деньги будут сконвертированы по курсу вашего банка, если валюта карты не доллары.

          {% note info %}

          Если вы используете кошелек в сервисе ЮMoney, то при переходе к оплате у вас могут запросить [платежный пароль](https://yandex.ru/support/money/password/permanent.html).

          {% endnote %}

      1. Отслеживайте поступление денег на счет:

          - В Толоке на странице [Профиль]({{ profile }}) (вкладка **История поступлений**).

          - В Яндекс Балансе на странице [Счета]({{ invoices }}).

    {% endlist %}

## Что дальше {#what_next}

- [Запустите пул](pool-run-and-stop.md).

## Решение проблем {#troubleshooting}

[Вернуть средства, перечисленные на счет в Толоку](../troubleshooting/support.md#feedback_khw_wc3_qjb)

[Получить закрывающие документы и акты](../troubleshooting/support.md#feedback_g3b_vj3_qjb)

Если деньги не поступили на счет в течение указанного срока:

{% include [contact-support](../_includes/contact-support.md) %}