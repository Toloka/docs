# Получить агрегированные ответы

{% include [announce](../_includes/announce.md) %}

Получает агрегированные ответы.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/aggregated-solutions/<operation_id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/aggregated-solutions/<operation_id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**operation_id** | Идентификатор операции.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}

#|
||**Параметр**| **Описание**||
||**sort** | **string**

Параметры для сортировки по возрастанию:

- `task_id` — идентификатор задания.

Чтобы изменить направление сортировки (сортировать по убыванию), добавьте знак дефиса перед параметром: `sort=-task_id`.||
||**Стандартные query-параметры** |
- **limit** (**integer** — ограничение на количество возвращаемых результатов. По умолчанию — 50, максимум — 300)
- **task_id_gt** (**string** — задания с идентификатором больше указанного значения)
- **task_id_gte** (**string** — задания с идентификатором, больше или равным указанному значению)
- **task_id_lt** (**string** — задания с идентификатором меньше указанного значения)
- **task_id_lte** (**string** — задания с идентификатором, меньше или равным указанному значению)||
|#

## Пример запроса {#request-example}

Можно настроить показ списка ответов частями (например, по 10 ответов):

1. Показать первые 10 ответов, начиная с ответа с наименьшим идентификатором задания.
1. Показывать оставшиеся ответы по 10 штук в порядке возрастания.

**Показать первые 10 ответов**

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/aggregated-solutions/<operation_id>?sort=task_id&limit=10
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/aggregated-solutions/<operation_id>?sort=task_id&limit=10
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

**Показывать остальные части с сортировкой по возрастанию идентификатора**

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/aggregated-solutions/<operation_id>?sort=task_id&limit=10&task_id_gt=<ID of the last task from the previous response>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/aggregated-solutions/<operation_id>?sort=task_id&limit=10&task_id_gt=<ID of the last task from the previous response>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

## Ответ {#response}

[Результат агрегации](aggregate-by-task.md) в массиве `items`.

```json
{"items" : [{task #1}, {task #2}, ... {task #n}], "has_more": true}
```