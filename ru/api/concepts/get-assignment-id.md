# Получить свойства ответа

{% include [announce](../_includes/announce.md) %}

Получает свойства данного ответа.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/assignments/<response_id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/assignments/<response_id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**response_id** | Идентификатор выдачи страницы заданий исполнителю.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

```json
{
  "id": "0000082301--5f69bcc046757f5cf86c12ff",
  "task_suite_id": "0000082301--5f69bc8446757f5cf86c0e24",
  "pool_id": "533249",
  "user_id": "b4d8bcc33403cae9eb69991c8bb90bdc",
  "status": "ACCEPTED",
  "reward": 0.01,
  "bonus_ids": "IDs of the bonuses given for the task",
  "tasks": [{
    "id": "6946cefa-32af-4f62-b530-8d2c71fa2966",
    "input_values": {
      "image": "https://images.com/1.png"
    }
  }],
  "solutions": [{
    "output_values": {
      "result": "OK"
    }
  }],
  "mixed": false,
  "automerged": false,
  "created": "2020-09-22T08:58:40.913",
  "submitted": "2020-09-22T08:58:46.207",
  "accepted": "2020-09-22T08:58:46.207",
  "public_comment": "Well done!",
  "owner": {
    "id": "ac1e4701364b4ccef8a4fe10a8980cff",
    "myself": true
  }
}
```

#|
||**Параметр**| **Описание**||
||**id** | **string**

Идентификатор выдачи страницы заданий исполнителю.||
||**task_suite_id** | **string**

Идентификатор страницы заданий.||
||**pool_id** | **string**

Идентификатор пула, в который входит страница заданий.||
||**user_id** | **string**

Идентификатор исполнителя, который получил страницу заданий.||
||**status** | **string**

Статус выданной страницы заданий:

- `ACTIVE` — выполняется исполнителем;
- `SUBMITTED` — выполнена, но не проверена;
- `ACCEPTED` — принята заказчиком;
- `REJECTED` — отклонена заказчиком;
- `SKIPPED` — пропущена исполнителем;
- `EXPIRED` — истек срок выполнения заданий.||
||**reward** | **integer**

Плата, которую получил исполнитель.||
||**public_comment** | **string**

Комментарий исполнителю.

Максимальная длина: 2048 символов.||
||**bonus_ids[]** | **array of strings**

`id` бонусов, выплаченных за задание.||
||**tasks[]** | **array of objects**

[Данные заданий](task-suite.md).||
||**first_declined_solution_attempt[]** | **array of objects**

Для обучающих заданий. Первоначальные ответы исполнителя в обучающем задании (только если эти ответы были неправильными). Если исполнитель ответил правильно с первой попытки, массив `first_declined_solution_attempt` отсутствует.

Массивы с ответами (`output_values`) расположены в том же порядке, что и данные заданий в массиве `tasks`.

```json
{
  "output_values": {
    "<field 1>": <response>,
    "<field 2>": <response>
     ...
    "<field N>": <response>
  },
  ...
}
```

||
||**solutions[]** | **array of objects**
Ответы исполнителя. Расположены в том же порядке, что и данные заданий в массиве `tasks`.

```json
{
  "output_values": {
    "<field 1>": <response>,
    "<field 2>": <response>
    ...
    "<field N>": <response>
  },
  ...
}
```

||
||**mixed** | **boolean**

Способ создания страницы заданий:

- `true` — автоматически («умное смешивание»);
- `false` — вручную.

По умолчанию `false`.

Подробнее о формировании страниц заданий см. в документе [Руководство заказчика](../../guide/concepts/pool-main.md).||
||**automerged** | **boolean**

Флаг ответа, полученного в результате [слияния идентичных заданий](tasks.md#task-merge). Значение:

- `true` — ответ записан в результате слияния идентичных заданий;
- `false` — обычный ответ исполнителя.||
||**created** | **string**

Дата и время, когда страница заданий была выдана исполнителю. Приводится по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**submitted** | **string**

Дата и время, когда страница заданий была выполнена исполнителем. Приводится по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**accepted** | **string**

Дата и время, когда ответы к странице заданий были приняты заказчиком. Приводится по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**rejected** | **string**

Дата и время, когда ответы к странице заданий были отклонены заказчиком. Приводится по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**skipped** | **string**

Дата и время, когда страница заданий была пропущена исполнителем. Приводится по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**expired** | **string**

Дата и время, когда время на выполнение страницы заданий истекло. Приводится по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**owner.id** | **string**

Идентификатор заказчика.||
||**owner.myself** | **boolean**

Проверяет, кому принадлежит объект:

- `true` — исполнителю, чей OAuth-токен указан в запросе;
- `false` — другому аккаунту (сотруднику или владельцу).||
|#