# Изменить приоритет страницы

Изменяет приоритет страницы заданий в пуле.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  PATCH https://toloka.yandex.com/api/v1/task-suites/<task_suite_id>
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

- Песочница

  ```bash
  PATCH https://sandbox.toloka.yandex.com/api/v1/task-suites/<task_suite_id>
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**task_suite_id** | Идентификатор страницы.


## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}


## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}


#|
||**Параметр**| **Описание**||
||**open_pool** | **boolean**

Открыть пул сразу после завершения операции, если пул закрыт. По умолчанию значение `false`.||
|#


## Тело запроса {#body}

```json
{
   "issuing_order_override": <new value>
}
```

#|
||**Параметр**| **Описание**||
||**issuing_order_override** | **float**

Приоритет страницы заданий среди других страниц в пуле. Определяет порядок выдачи страниц исполнителям. Чем больше значение параметра, тем выше приоритет.
Параметр можно использовать, если в пуле `issue_task_suites_in_creation_order: true`.
Возможные значения: от `-99999.99999` до `99999.99999`.
По умолчанию значение `0`.||
|#


## Ответ {#response}

Содержит [страницу заданий в формате JSON](task-suite.md).
