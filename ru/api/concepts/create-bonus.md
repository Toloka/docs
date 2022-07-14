# Выдать бонусы

Выдает бонусы исполнителям.

{% include [bonus-sum](../_includes/concepts/bonus/id-bonus/sum.md) %}

{% note alert %}

Вы можете отправить не более 10 000 таких запросов в день.

{% endnote %}

В одном запросе нельзя передавать одному толокеру несколько бонусов с одинаковой ценой, названием и сообщением. Будет возвращен ответ со статусом 409.

{% cut "Пример ошибки c HTTP статусом 409" %}

```json
{
  "user_id": {
    "code": "ENTITY_CONFLICT",
    "message": "It is not allowed to apply multiple bonuses with the same amount, title, message and comment to same user in single operation"
  }
}
```

{% endcut %}

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    POST https://toloka.yandex.com/api/v1/user-bonuses
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Песочница

    ```bash
    POST https://sandbox.toloka.yandex.com/api/v1/user-bonuses
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}

#|
||**Параметр**| **Описание**||
||**async_mode** | **boolean**

Способ обработки запроса:

- `true` — отложенный. В результате запроса создается асинхронная операция, выполняемая в фоновом режиме. Ответ содержит сведения об операции (время начала и окончания, статус, количество бонусов).
- `false` — синхронный. Ответ содержит сведения о выданных бонусах. В одном запросе можно отправить не более 100 бонусов.

По умолчанию значение `false`.||
||**assignment_id** | **string**

Идентификатор ответа исполнителя на задание, за которое выплачивается бонус.||
||**skip_invalid_items** | **boolean**

Параметры валидации JSON-объектов:

- `true` — выдать бонус, если JSON-объект со сведениями о бонусе прошел валидацию. В противном случае пропустить выдачу бонуса.
- `false` — остановить операцию и не выдавать бонусы, если хотя бы один JSON-объект не прошел валидацию.

По умолчанию значение `false`.||
||**operation_id** | **string**

Идентификатор операции. Можно использовать при любом способе обработки запроса.||
|#

## Тело запроса {#body}

```json
{
  "user_id": "21c4f092ebad180cf56b9babe0ef9f19",
  "amount": 1.5,
  "assignment_id": "6946cefa-32af-4f62-b530-8d2c71fa2966",
  "private_comment": "Good job!",
  "public_title": {
    "EN": "Completed tasks"
  },
  "public_message": {
    "EN": "10 tasks successfully completed"
  },
  "without_message": false
}
```

#|
||**Параметр**| **Описание**||
||**user_id** | **string**

Обязательный параметр. Идентификатор исполнителя.||
||**amount** | **float**

Обязательный параметр. Сумма бонуса в долларах.||
||**assignment_id** | **string**

Идентификатор ответа исполнителя на задание, за которое выплачивается бонус.||
||**private_comment** | **string**

Комментарий, доступный только заказчику.||
||**public_title** | **object**

Заголовок сообщения для исполнителя. Может быть на нескольких языках (сообщение придет на языке исполнителя). Формат: "`<язык RU/EN/TR/ID/FR>": "<текст заголовка>`".||
||**public_message** | **object**

Текст сообщения для исполнителя. Может быть текст на нескольких языках (сообщение придет на языке исполнителя). Формат: `"<язык RU/EN/TR/ID/FR>": "<текст сообщения>"`.||
||**without_message** | **boolean**

Позволяет не отправлять исполнителю сообщение о бонусе. По умолчанию `false`.

Для того чтобы выдать бонус без сообщения, нужно указать `null` для `public_title` и `public_message` и `true` для `without_message`.||
|#

## Ответ {#response}

Формат ответа зависит от значения query-параметра `async_mode`.

{% list tabs %}

- Сведения о бонусах (async_mode=false)

  ```json
  {
    "items": {
      "0": {details of a reward #0},
      "2": {details of a reward #2},
      "<N>": {details of a reward #N}
    },
    "validation_errors": {
      "1": {validation errors for a reward #1},
      "3": {validation errors for a reward #3},
      "<N>": {validation errors for a reward #N}
    }
  }
  ```

  #|
  ||**Параметр**| **Описание**||
  ||**items** | **string**

  Объект со сведениями о выданных бонусах.||
  ||**validation_errors** | **string**

  Объект с ошибками валидации. Возвращается, если в запросе используется параметр `skip_invalid_items=true`.||
  |#

- Сведения об операции (async_mode=true)

  ```json
  {
    "id": "26e130ad3652443a3dc5094791e48ef9",
    "type": "USER_BONUS.BATCH_CREATE",
    "status": "SUCCESS",
    "submitted": "2020-12-13T23:32:01",
    "started": "2020-12-13T23:33:00",
    "finished": "2020-12-13T23:34:12",
    "parameters": {
      "skip_invalid_items": true
    },
    "details": {
      "total_count": 2,
      "valid_count": 2,
      "not_valid_count": 0,
      "success_count": 2,
      "failed_count": 0
    }
  }
  ```

  #|
  ||**Параметр**| **Описание**||
  ||**id** | **string**

  Идентификатор операции.||
  ||**type** | **string**

  Тип операции `USER_BONUS.BATCH_CREATE` — выплата бонусов нескольким исполнителям.||
  ||**status** | **string**

  Статус операции:

  - `PENDING` — выполнение не началось;
  - `RUNNING` — выполняется;
  - `SUCCESS` — успешно выполнена;
  - `FAIL` — не выполнена.||
  ||**submitted** | **string**

  Дата и время отправки запроса по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
  ||**started** | **string**

  Дата и время начала операции по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
  ||**finished** | **string**

  Дата и время окончания операции по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
  ||**parameters** | **object**

  Параметры операции в запросе.||
  ||**skip_invalid_items** | **boolean**

  Параметры валидации JSON-объектов:

  - `true` — выдать бонус, если JSON-объект со сведениями о бонусе прошел валидацию. В противном случае пропустить выдачу бонуса.
  - `false` — остановить операцию и не выдавать бонусы, если хотя бы один JSON-объект не прошел валидацию.

  По умолчанию значение `false`.||
  ||**details** | **object**

  Сведения о выполнении операции.||
  ||**details.total_count** | **integer**

  Количество бонусов в запросе.||
  ||**details.valid_count** | **integer**

  Количество JSON-объектов со сведениями о бонусе, которые прошли валидацию.||
  ||**details.not_valid_count** | **integer**

  Количество JSON-объектов со сведениями о бонусе, которые не прошли валидацию.||
  ||**details.success_count** | **integer**

  Количество выданных бонусов.||
  ||**details.failed_count** | **integer**

  Количество бонусов, которые не были выданы.||
  |#

{% endlist %}