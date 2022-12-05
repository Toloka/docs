# Формат уведомлений

{% include [deprecate](../../_includes/deprecate.md) %}

Как только произойдет событие, для которого [создана подписка](put-webhook-subscriptions.md), на указанный в подписке URL придет уведомление. В нем будут все данные об объекте на момент, когда произошло событие.

Уведомления приходят в формате JSON.

```json
{
  "events":
    [
      {Event data 1},
      {Event data 2},
      {Event data N}
    ]
}
```

Содержащиеся в уведомлении данные зависят от типа события:

- `POOL_CLOSED` — пул закрыт.
- `DYNAMIC_OVERLAP_COMPLETED` — появилась агрегированная оценка по динамическому перекрытию.
- `ASSIGNMENT_CREATED` — задание создано.
- `ASSIGNMENT_SUBMITTED` — задание выполнено и ожидает приемки заказчиком.
- `ASSIGNMENT_SKIPPED` — задание было взято в работу, но исполнитель пропустил его и к нему уже не вернется.
- `ASSIGNMENT_EXPIRED` — задание было взято в работу, но исполнитель не успел выполнить его за отведенное время или отказался от него до конца срока.
- `ASSIGNMENT_APPROVED` — задание выполнено исполнителем и подтверждено заказчиком.
- `ASSIGNMENT_REJECTED` — задание выполнено исполнителем, но отклонено заказчиком.


Если при создании подписки указан параметр **secret_key**, то в заголовках уведомлений о событии появится дополнительный заголовок **Toloka-Signature**. Он подтверждает, что запросы были отправлены с помощью API Toloka. Подробнее см. в разделе [Аутентификация событий](authentication.md).

## Пример тела уведомления POOL_CLOSED {#pool-closed}

```json
{
  "uuid": "uuid-1",
  "event_time": "2020-02-14T12:22:58",
  "project_id": "project-1",
  "pool_id": "pool-1",
  "close_reason": "MANUAL",
  "webhook_subscription_id": "subscription-1",
  "type": "POOL_CLOSED"
}
```

#|
||**Параметр**| **Описание**||
||**uuid** | **string**

Уникальный идентификатор события.||
||**event_time** | **string**

Время наступления события.||
||**project_id** | **string**

Идентификатор проекта, для которого создан пул.||
||**pool_id** | **string**

Идентификатор пула, для которого создана подписка.||
||**close_reason** | **string**

Причина закрытия пула.||
||**webhook_subscription_id** | **string**

Идентификатор подписки.||
||**type** | **string**

Тип события.
Возможное значение: `POOL_CLOSED` — пул закрыт.||
|#

## Пример тела уведомления ASSIGNMENT_CREATED {#assignment}

```json
{
  "uuid": "uuid-1",
  "event_time": "2020-02-14T12:23:05",
  "project_id": "project-1",
  "pool_id": "pool-1",
  "task_suite_id": "task suite-1",
  "assignment_id": "assignment-1",
  "webhook_subscription_id": "subscription-1",
  "type": "ASSIGNMENT_CREATED"
}
```

#|
||**Параметр**| **Описание**||
||**uuid** | **string**

Уникальный идентификатор события.||
||**event_time** | **string**

Время наступления события.||
||**project_id** | **string**

Идентификатор проекта, для которого создан пул.||
||**pool_id** | **string**

Идентификатор пула, для которого создана подписка.||
||**task_suite_id** | **string**

Идентификатор набора заданий.||
||**assignment_id** | **string**

Идентификатор выдачи набора заданий исполнителю.||
||**webhook_subscription_id** | **string**

Идентификатор подписки.||
||**type** | **string**

Тип события.
Возможные значения:

- `ASSIGNMENT_CREATED` — задание создано.
- `ASSIGNMENT_SUBMITTED` — задание выполнено и ожидает приемки заказчиком.
- `ASSIGNMENT_SKIPPED` — задание было взято в работу, но исполнитель пропустил его и к нему уже не вернется.
- `ASSIGNMENT_EXPIRED` — задание было взято в работу, но исполнитель не успел выполнить его за отведенное время или отказался от него до конца срока.
- `ASSIGNMENT_APPROVED` — задание выполнено исполнителем и подтверждено заказчиком.
- `ASSIGNMENT_REJECTED` — задание выполнено исполнителем, но отклонено заказчиком.
||
|#

## Пример тела уведомления DYNAMIC_OVERLAP_COMPLETED {#dynamic-overlap-completed}

```json
{
  "uuid": "uuid-1",
  "event_time": "2020-02-14T12:23:05",
  "project_id": "project-1",
  "pool_id": "pool-2",
  "task_id": "task-1",
  "confidence": 0.155,
  "webhook_subscription_id": "subscription-1",
  "type": "DYNAMIC_OVERLAP_COMPLETED",
  "assignment_ids": ["assignment-1", "assignment-2"],
  "output_values": {
    "field_one": "value-1"
  }
}
```

#|
||**Параметр**| **Описание**||
||**uuid** | **string**

Уникальный идентификатор события.||
||**event_time** | **string**

Время наступления события.||
||**project_id** | **string**

Идентификатор проекта, для которого создан пул.||
||**pool_id** | **string**

Идентификатор пула, для которого создана подписка.||
||**task_id** | **string**

Идентификатор задания.||
||**confidence** | **integer**

Уверенность в агрегированном ответе.||
||**webhook_subscription_id** | **string**

Идентификатор подписки.||
||**type** | **string**

Тип события.
Возможное значение: `DYNAMIC_OVERLAP_COMPLETED` — появилась агрегированная оценка по динамическому перекрытию.||
||**assignment_ids[]** | **array of strings**

Идентификаторы выдач набора заданий исполнителям.||
||**output_values[]** | **array of objects**

Поля выходных данных, содержащие текст задания (`field_one`) и ответ.||
|#