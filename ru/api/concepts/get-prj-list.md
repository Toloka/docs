# Получить список проектов

{% include [announce](../_includes/announce.md) %}

Получает список проектов.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/projects
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/projects
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}

#|
||Параметр | Описание||
||**status** | **string**

Статус проекта:

- `ACTIVE` — активный;
- `ARCHIVED` — архивный.||
||**sort** | **string**

Параметры для сортировки:

- `id` — идентификатор проекта;
- `created` — дата создания проекта по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`;
- `public_name` — название проекта;
- `private_comment` — комментарий к проекту.

{% include [get-tasks-list-about-sorting](../_includes/concepts/get-tasks-list/id-get-tasks-list/about-sorting.md) %}||
||**owner** | **string**

Идентификатор заказчика.||
||**Стандартные query-параметры** |
- **limit** (**integer** — ограничение на количество возвращаемых результатов. По умолчанию — 50, максимум — 300)
- **id_gt** (**string** — объекты с идентификатором больше указанного значения)
- **id_gte** (**string** — объекты с идентификатором больше или равным указанному значению)
- **id_lt** (**string** — объекты с идентификатором меньше указанного значения)
- **id_lte** (**string** — объекты с идентификатором меньше или равным указанному значению)
- **created_gt** (**string** — объекты, выданные или созданные после указанной даты)
- **created_gte** (**string** — объекты, выданные или созданные после указанной даты включительно)
- **created_lt** (**string** — объекты, выданные или созданные до указанной даты)
- **created_lte** (**string** — объекты, выданные или созданные до указанной даты включительно)||
|#

## Пример запроса {#request-example}

Можно настроить показ перечня проектов частями (например, по 10 проектов):

1. Показать первые 10 проектов, начиная с проекта с наименьшим идентификатором.
1. Показывать оставшиеся проекты по 10 штук в порядке возрастания.

**Показать первые 10 проектов**

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/projects?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/projects?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

**Показывать остальные части с сортировкой по возрастанию идентификатора**

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/projects?sort=id&limit=10&id_gt=<ID of the last project from the previous response>
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/projects?sort=id&limit=10&id_gt=<id of the last project from the previous response>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Ответ {#response}

Содержит список проектов и их свойства в массиве `items`:

```json
{"items": [{properties of project 1}, {properties of project 2}, ... {properties of project n}], "has_more": false}
```