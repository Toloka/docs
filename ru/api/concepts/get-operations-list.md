# Получить список операций

Получает список созданных операций.

## Запрос {#query}

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/operations
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/operations
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}



#|
||**Параметр**| **Описание**||
||**type** | **string**

Тип операции:
- `POOL.OPEN` — открытие пула;
- `POOL.CLOSE` — закрытие пула;
- `PROJECT.ARCHIVE` — отправка проекта в архив;
- `POOL.ARCHIVE` — отправка пула в архив;
- `TASK_SUITE.BATCH_CREATE` — создание нескольких страниц заданий;
- `KNOWN_SOLUTIONS.GENERATE` — генерация контрольных заданий.||
||**status** | **string**

Статус операции:
- `PENDING` — выполнение не началось;
- `RUNNING` — выполняется;
- `SUCCESS` — успешно выполнена;
- `FAIL` — не выполнена.||
||**sort** | **string**

Параметры для сортировки:
- `id` — идентификатор операции;
- `submitted` — дата и время отправки запроса по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`;
- `finished` — дата и время завершения операции по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.

{% include [get-tasks-list-about-sorting](../_includes/concepts/get-tasks-list/id-get-tasks-list/about-sorting.md) %}||
||**Стандартные query-параметры** |
- **limit** (**integer** — ограничение на количество возвращаемых результатов. По умолчанию — 50, максимум — 300)
- **id_gt** (**string** — объекты с идентификатором больше указанного значения)
- **id_gte** (**string** — объекты с идентификатором больше или равным указанному значению)
- **id_lt** (**string** — объекты с идентификатором меньше указанного значения)
- **id_lte** (**string** — объекты с идентификатором меньше или равным указанному значению)
- **submitted_gt** (**string** — объекты, выданные или созданные после указанной даты)
- **submitted_gte** (**string** — объекты, выданные или созданные после указанной даты включительно)
- **submitted_lt** (**string** — объекты, выданные или созданные до указанной даты)
- **submitted_lte** (**string** — объекты, выданные или созданные до указанной даты включительно)
- **finished_gt** (**string** — объекты, завершенные после указанной даты)
- **finished_gte** (**string** — объекты, завершенные после указанной даты включительно)
- **finished_lt** (**string** — объекты, завершенные до указанной даты)
- **finished_lte** (**string** — объекты, завершенные до указанной даты включительно)||
|#


## Ответ {#response}

Содержит список операций в массиве `items`:

```json
{"items": [{operation details 1}, {operation details 2}, ... {operation details n}], "has_more": false}
```
