# Получить подписку

{% include [announce](../_includes/announce.md) %}

Получает данные подписки.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/webhook-subscriptions/<subscription_id>
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/webhook-subscriptions/<subscription_id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**subscription_id** | Идентификатор подписки.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

Содержит информацию о запрашиваемой подписке в формате JSON.

```json
[
  {
    "webhook_url": "https://awesome-requester.com/toloka-webhook",
    "event_type": "ASSIGNMENT_CREATED",
    "pool_id": "121212",
    "id": "webhook-subscription-1",
    "created": "2020-02-03T15:00:00"
  }
]
```

#|
||**Параметр**| **Описание**||
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
- `ASSIGNMENT_REJECTED` — задание выполнено исполнителем, но отклонено заказчиком.||
||**pool_id** | **string**

Идентификатор пула, для которого создана подписка.||
||**id** | **string**

Идентификатор подписки. Формируется автоматически.||
||**created** | **string**

Дата и время создания подписки (по UTC). Формат даты ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
|#