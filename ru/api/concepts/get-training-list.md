# Получить список обучений

{% include [announce](../_includes/announce.md) %}

Получает список созданных обучений (в том числе архивных).

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/trainings
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/trainings
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}


#|
||**Параметр**| **Описание**||
||**status** | **string**

Статус обучающего пула:

- `OPEN` — открыт;
- `CLOSED` — закрыт;
- `LOCKED` — заблокирован: невозможны никакие действия;
- `ARCHIVED` — архивный.||
||**project_id** | **string**
Идентификатор проекта, к которому относится обучающий пул.||
||**sort** | **string**

Параметры для сортировки по возрастанию:

- `id` — идентификатор обучающего пула;
- `created` — дата создания обучающего пула по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`;
- `last_started` — дата последнего запуска обучающего пула в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.

{% include [get-tasks-list-about-sorting](../_includes/concepts/get-tasks-list/id-get-tasks-list/about-sorting.md) %}||
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
- **last_started_gt** (**string** — объекты, которые были в последний раз открыты после указанной даты)
- **last_started_gte** (**string** — объекты, которые были в последний раз открыты после указанной даты включительно)
- **last_started_lt** (**string** — объекты, которые были в последний раз открыты до указанной даты)
- **last_started_lte** (**string** — объекты, которые были в последний раз открыты раньше указанной даты включительно)||
|#

## Пример запроса {#request-example}

Можно настроить показ списка обучающих пулов частями (например, по 10 пулов):

1. Показать первые 10 пулов, начиная с пула с наименьшим идентификатором.
1. Показывать оставшиеся пулы по 10 штук в порядке возрастания.

**Показать первые 10 пулов**

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/trainings?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/trainings?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

**Показывать остальные части с сортировкой по возрастанию идентификатора**

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/trainings?sort=id&limit=10&id_gt=<id of the last training from the previous response>
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/trainings?sort=id&limit=10&id_gt=<id of the last training from the previous response>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Ответ {#response}

Содержит список обучающих пулов и их свойств в массиве `items`:

```json
{"items" : [{parameters_of_training_pool_1}, {parameters_of_training_pool_2}, ... {parameters_of_training_pool__n_}], "has_more": false}
```