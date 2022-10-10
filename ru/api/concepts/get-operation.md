# Получить сведения об операции

{% include [announce](../_includes/announce.md) %}

Получает сведения об операции.

## Запрос {#query}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/operations/<operation_id>
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/operations/<operation_id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**operation_id** | Идентификатор операции.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

Содержит сведения об операции в формате JSON (см. пример в разделе [Операции](operations.md)).

```json
{
  "id" : "57068577e4b0bf7b07a0256f",
  "type" : "TASK_SUITE.BATCH_CREATE",
  "status" : "FAIL",
  "submitted" : "2016-04-07T16:06:15.902",
  "started" : "2016-04-07T16:06:15.902",
  "finished" : "2016-04-07T16:06:15.902",
  "progress" : 100,
  "parameters" : {
    "open_pool" : fase,
    "allow_defaults" : false,
    "skip_invalid_items" : false
  },
  "details" : {
    "total_count" : 2,
    "valid_count" : 0,
    "failed_count" : 2,
    "success_count" : 0,
    "not_valid_count" : 2
  }
}
```

#|
||**Параметр**| **Описание**||
||**id** | **string \| обязательный**

Идентификатор операции.||
||**type** | **string \| обязательный**

Тип операции:

- `POOL.OPEN` — открытие пула.
- `POOL.CLOSE` — закрытие пула.
- `PROJECT.ARCHIVE` — отправка проекта в архив.
- `POOL.ARCHIVE` — отправка пула в архив.
- `SOLUTION.AGGREGATE` — агрегация ответов.
- `TASK_SUITE.BATCH_CREATE` — создание нескольких страниц заданий;
- `KNOWN_SOLUTIONS.GENERATE` — генерация контрольных заданий.||
||**status** | **string \| обязательный**

Статус операции:

- `PENDING` — выполнение не началось.
- `RUNNING` — выполняется.
- `SUCCESS` — успешно выполнена.
- `FAIL` — не выполнена.

Отображается для всех операций, кроме создания пула.||
||**submitted** | **string \| обязательный**

Дата и время отправки запроса по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**started** | **string**

Дата и время начала операции по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**finished** | **string**

Дата и время завершения операции по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**progress** | **integer**

Ход выполнения операции в процентах.||
||**parameters** | **JSON**

Параметры операции (зависят от типа операции).||
||**details** | **JSON**

Детали выполнения операции.||
|#

Подробного описания ошибок в ответе нет. Если произошла ошибка, [запросите лог операции](get-operation-log.md).