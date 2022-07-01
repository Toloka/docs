# Получить список страниц заданий

Получает список страниц заданий в пуле.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/task-suites
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/task-suites
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}


#|
||**Параметр**| **Описание**||
||**pool_id** | **string**

Идентификатор пула, из которого нужно получить страницы заданий.
Обязательно указать `task_id`, либо`pool_id`.||
||**task_id** | **string**

Идентификатор задания на страницах, сформированных автоматически (с помощью «умного смешивания»). Вы получите страницы заданий, на которых есть указанное задание.
Обязательно указать `task_id`, либо`pool_id`.||
||**sort** | **string**

Параметры для сортировки:
- `id` — идентификатор страницы заданий;
- `created` — дата создания страницы заданий по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].

{% include [get-tasks-list-about-sorting](../_includes/concepts/get-tasks-list/id-get-tasks-list/about-sorting.md) %}||
||**overlap** | **integer**

Страницы с перекрытием, равным указанному значению.||
||**Стандартные query-параметры** |
- **limit** (**integer** — ограничение на количество возвращаемых результатов. По умолчанию — 50, максимум — 300)
- **id_gt** (**string** — объекты с идентификатором больше указанного значения)
- **id_gte** (**string** — объекты с идентификатором больше или равным указанному значению)
- **id_lt** (**string** — объекты с идентификатором меньше указанного значения)
- **id_lte** (**string** — объекты с идентификатором меньше или равным указанному значению)
- **created_gt** (**string** — объекты, выданные или созданные после указанной даты)
- **created_gte** (**string** — объекты, выданные или созданные после указанной даты включительно)
- **created_lt** (**string** — объекты, выданные или созданные до указанной даты)
- **created_lte** (**string** — объекты, выданные или созданные до указанной даты включительно)
- **overlap_gt** (**integer** — объекты с перекрытием больше указанного значения)
- **overlap_gte** (**integer** — объекты с перекрытием, больше или равным указанному значению)
- **overlap_lt** (**integer** — объекты с перекрытием меньше указанного значения)
- **overlap_lte** (**integer** — объекты с перекрытием, меньше или равным указанному значению)||
|#

## Пример запроса {#request-example}

Можно настроить показ перечня страниц заданий частями (например, по 10 страниц):

1. Показать первые 10 страниц заданий, начиная со страницы с наименьшим идентификатором.
1. Показывать оставшиеся страницы заданий по 10 штук в порядке возрастания.

**Показать первые 10 страниц заданий**

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/task-suites?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/task-suites?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

**Показывать остальные части с сортировкой по возрастанию идентификатора**

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/task-suites?sort=id&limit=10&id_gt=<id of the last task suite from the previous response>
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/task-suites?sort=id&limit=10&id_gt=<id of the last task suite from the previous response>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Ответ {#response}

Содержит страницы заданий в массиве `items`:

```json
{"items" : [{task suite 1}, {task suite 2}, ... {task suite n}], "has_more": true}
```
