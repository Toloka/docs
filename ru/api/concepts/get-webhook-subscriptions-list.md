# Получить перечень подписок

Получает данные по нескольким созданным подпискам.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/webhook-subscriptions
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/webhook-subscriptions
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}


#|
||**Параметр**| **Описание**||
||**event_type** | **string**

Тип события.
Возможные значения:
- `POOL_CLOSED` — пул закрыт.
- `DYNAMIC_OVERLAP_COMPLETED` — появилась агрегированная оценка по динамическому перекрытию.
- `ASSIGNMENT_CREATED` — задание создано.
- `ASSIGNMENT_SUBMITTED` — задание выполнено и ожидает приемки заказчиком.
- `ASSIGNMENT_SKIPPED` — задание было взято в работу, но исполнитель пропустил его и к нему уже не вернется.
- `ASSIGNMENT_EXPIRED` — задание было взято в работу, но исполнитель не успел выполнить его за отведенное время или отказался от него до конца срока.
- `ASSIGNMENT_APPROVED` — задание выполнено исполнителем и подтверждено заказчиком.
- `ASSIGNMENT_REJECTED` — задание выполнено исполнителем, но отклонено заказчиком.||
||**pool_id** | **string**

Идентификатор пула, для которого запрашивается информация о подписках.||
||**sort** | **string**

Параметры для сортировки:
- `id` — идентификатор подписки;
- `created` — дата создания подписки по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].

{% include [get-tasks-list-about-sorting](../_includes/concepts/get-tasks-list/id-get-tasks-list/about-sorting.md) %}||
||**Стандартные query-параметры** |
- **limit**  (**integer** — ограничение на количество возвращаемых результатов. По умолчанию — 50, максимум — 300)
- **id_gt**  (**string** — объекты с идентификатором больше указанного значения)
- **id_gte**  (**string** — объекты с идентификатором больше или равным указанному значению)
- **id_lt**  (**string** — объекты с идентификатором меньше указанного значения)
- **id_lte**  (**string** — объекты с идентификатором меньше или равным указанному значению)
- **created_gt**  (**string** — объекты, выданные или созданные после указанной даты)
- **created_gte**  (**string** — объекты, выданные или созданные после указанной даты включительно)
- **created_lt**  (**string** — объекты, выданные или созданные до указанной даты)
- **created_lte**  (**string** — объекты, выданные или созданные до указанной даты включительно)||
|#

## Пример запроса {#request-example}
 Можно настроить показ перечня подписок частями (например, по 10 подписок):
1. Показать первые 10 подписок, начиная с подписки с наименьшим идентификатором.
1. Показывать оставшиеся подписки по 10 штук в порядке возрастания.

**Показать первые 10 подписок**

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/webhook-subscriptions?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/webhook-subscriptions?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

**Показывать остальные части с сортировкой по возрастанию идентификатора**

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/webhook-subscriptions?sort=id&limit=10&id_gt=<ID of the last subsciption from the previous response>
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/webhook-subscriptions?sort=id&limit=10&id_gt=<ID of the last subsciption from the previous response>
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

## Ответ {#response}

Содержит перечень подписок с информацией о каждой из них в формате JSON.

```json
{
  items: [
    {
       "webhook_url": "https://awesome-requester.com/toloka-webhook",
       "event_type": "ASSIGNMENT_CREATED",
       "pool_id": "121212",
       "id": "webhook-subscription-1",
       "created": "2020-02-03T15:00:00"
    },
    {
       "webhook_url": "https://awesome-requester.com/toloka-webhook",
       "event_type": "POOL_CLOSED",
       "pool_id": "121212",
       "id": "webhook-subscription-2",
       "created": "2020-02-03T15:00:00"
    }
  ],
  has_more: false
}
```

#|
||**Параметр**| **Описание**||
||**items[]** | **array of objects**

Массив объектов с информацией о запрашиваемых подписках.||
||**webhook_url** | **string**

URL, на который будут приходить уведомления.||
||**event_type** | **string**

Тип события.
Возможные значения:
- `POOL_CLOSED` — пул закрыт.
- `DYNAMIC_OVERLAP_COMPLETED` — появилась агрегированная оценка по динамическому перекрытию.
- `ASSIGNMENT_CREATED` — задание создано.
- `ASSIGNMENT_SUBMITTED` — задание выполнено и ожидает приемки заказчиком.
- `ASSIGNMENT_SKIPPED` — задание было взято в работу, но исполнитель пропустил его и к нему уже не вернется.
- `ASSIGNMENT_EXPIRED` — задание было взято в работу, но исполнитель не успел выполнить его за отведенное время или отказался от него до конца срока.
- `ASSIGNMENT_APPROVED` — задание выполнено исполнителем и подтверждено заказчиком.
- `ASSIGNMENT_REJECTED` — задание выполнено исполнителем, но отклонено заказчиком.
||
||**pool_id** | **string**

Идентификатор пула, для которого создана подписка.||
||**id** | **string**<

Идентификатор подписки.||
||**created** | **string**

Дата и время по создания подписки (по UTC). Формат даты ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
||**has_more** | **boolean**

Полнота списка.
Возможные значения:
- `true` — в выдачу включены не все элементы из-за ограничения параметра `limit`;
- `false` — выдача включает в себя исчерпывающий список элементов.
||
|#
