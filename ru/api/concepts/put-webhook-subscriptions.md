# Создать подписку

{% include [announce](../_includes/announce.md) %}

Создает одну или несколько подписок.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    PUT https://toloka.dev/api/v1/webhook-subscriptions
    Authorization: ApiKey PlaceYourRealApiKey_Here
    Content-Type: application/json
    ```

- Песочница

    ```bash
    PUT https://sandbox.toloka.dev/api/v1/webhook-subscriptions
    Authorization: ApiKey PlaceYourRealApiKey_Here
    Content-Type: application/json
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

```json
[
  {
     "webhook_url": "https://awesome-requester.com/toloka-webhook",
     "event_type": "ASSIGNMENT_CREATED",
     "pool_id": "121212"
  },
  {
     "webhook_url": "https://awesome-requester.com/toloka-webhook",
     "event_type": "POOL_CLOSED",
     "pool_id": "121212",
     "secret_key": "12345"
  }
]
```

#|
||**Параметр**| **Описание**||
||**webhook_url** | **string \| обязательный**

URL, на который будут приходить уведомления.||
||**event_type** | **string \| обязательный**

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
||**pool_id** | **string \| обязательный**

Идентификатор пула, для которого создается подписка.||
||**secret_key** | **string \| необязательный**
Секретный ключ, который позволяет проверить, что входящие запросы были отправлены с помощью API Toloka. Подробнее см. в разделе [Аутентификация событий](authentication.md).||
|#

## Ответ {#response}

Содержит информацию о созданных подписках в формате JSON. Каждой подписке присваивается уникальный идентификатор (`id`) и дата создания (`created`).

#### При создании одной подписки

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

#### При создании нескольких подписок

```json
{
  "items": [
    "0": {
      "webhook_url": "https://awesome-requester.com/toloka-webhook",
      "event_type": "ASSIGNMENT_CREATED",
      "pool_id": "121212",
      "id": "webhook-subscription-1",
      "created": "2020-02-03T15:00:00"
    },
    "1": {
      "webhook_url": "https://awesome-requester.com/toloka-webhook",
      "event_type": "POOL_CLOSED",
      "pool_id": "121212",
      "id": "webhook-subscription-2",
      "created": "2020-02-03T15:00:00"
    }
  ],
  "validation_errors": {}
}
```

#|
||**Параметр**| **Описание**||
||**items[]** | **array of objects**

Массив объектов с информацией о созданных подписках.||
||**<n>** | **object**

Порядковый номер подписки в запросе на создание (начиная с 0).||
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
||**validation_errors** | **object**

Объект с валидационными ошибками.||
|#