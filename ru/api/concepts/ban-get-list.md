# Получить список блокировок

{% include [announce](../_includes/announce.md) %}

Получает список блокировок исполнителя.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/user-restrictions
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-restrictions
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}

#|
||**Параметр**| **Описание**||
||**scope** | **string**

Область блокировки:

- `ALL_PROJECTS` — все проекты заказчика;
- `PROJECT` — проект (указывается `project_id`);
- `POOL` — пул (указывается `pool_id`);
- `SYSTEM` — исполнители, которые выполняли задания заказчика, но были [заблокированы на платформе](../../guide/concepts/ban.md#ban-platform).||
||**user_id** | **string**

Идентификатор исполнителя.||
||**project_id** | **string \| обязательный при условии**

Обязателен, если `scope=PROJECT`.

Идентификатор проекта, к которому заблокирован доступ.||
||**pool_id** | **string \| обязательный при условии**

Обязателен, если `scope=POOL`.

Идентификатор пула, к которому заблокирован доступ.||
||**sort** | **string**

Параметры для сортировки:

- `id` — идентификатор;
- `created` — дата создания по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.

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
- **created_lte** (**string** — объекты, выданные или созданные до указанной даты включительно)||
|#

## Пример запроса {#request-example}

Чтобы получить список блокировок частями (например, по 10 блокировок), используйте комбинацию параметров в запросах:

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/user-restrictions?sort=id&limit=10
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

    ```bash
    GET https://toloka.dev/api/v1/user-restrictions?sort=id&limit=10&id_gt=<id last ban from the answer to the previous query>
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-restrictions?sort=id&limit=10
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-restrictions?sort=id&limit=10&id_gt=<id last ban from the answer to the previous query>
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

{% endlist %}

## Ответ {#response}

Содержит список блокировок в массиве `items`:

```json
{"items" : [{ban parameters 1}, {ban parameters 2}, ... {ban parameters n}], "has_more": true}
```