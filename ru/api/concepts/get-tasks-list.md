# Получить список заданий

Получает список заданий в пуле.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/tasks
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/tasks
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}


#|
||**Параметр**| **Описание**||
||**pool_id** | **string \| обязательный**

Идентификатор пула, из которого нужно получить задания.||
||**sort** | **string**

Параметры для сортировки:

- `id` — идентификатор задания;
- `created` — дата создания задания по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].
О том, как задать сортировку, читайте на странице [Сортировка списка объектов](sorting.md).||
||**overlap** | **integer**

Задания с перекрытием, равным указанному значению.||
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
 Можно настроить показ списка заданий частями (например, по 10 заданий):
1. Показать первые 10 заданий, начиная с подписки с наименьшим идентификатором.
1. Показывать оставшиеся задания по 10 штук в порядке возрастания.

**Показать первые 10 заданий**

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/tasks?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/tasks?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

**Показывать остальные части с сортировкой по возрастанию идентификатора**

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/tasks?sort=id&limit=10&id_gt=<ID of the last task from the previous response>
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/tasks?sort=id&limit=10&id_gt=<ID of the last task from the previous response>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Ответ {#response}

Содержит данные заданий в массиве `items`:

```json
{"items" : [{task 1}, {task 2}, ... {task n}], "has_more": true}
```
