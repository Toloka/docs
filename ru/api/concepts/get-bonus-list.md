# Получить список выданных бонусов

{% include [announce](../_includes/announce.md) %}

Получает список выданных бонусов.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/user-bonuses
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-bonuses
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}

#|
||**Параметр**| **Описание**||
||**user_id** | **string**

Идентификатор исполнителя.||
||**assignment_id** | **string**

Идентификатор ответа исполнителя на задание, за которое выплачивается бонус.||
||**private_comment** | **string**

Комментарий, доступный только заказчику.||
||**sort** | **string**

Параметры для сортировки:

- `id` — идентификатор бонуса;
- `created` — дата выдачи бонуса по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.

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

Можно настроить показ списка бонусов частями (например, по 10 бонусов):

1. Показать первые 10 бонусов, начиная с бонуса с наименьшим идентификатором.
1. Показывать оставшиеся бонусы по 10 штук в порядке возрастания.

**Показать первые 10 бонусов**

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/user-bonuses?sort=id&limit=10
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-bonuses?sort=id&limit=10
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

**Показывать остальные части с сортировкой по возрастанию идентификатора**

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/user-bonuses?sort=id&limit=10&id_gt=<ID of the last bonus from the previous response>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-bonuses?sort=id&limit=10&id_gt=<ID of the last bonus from the previous response>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

## Ответ {#response}

[Сведения о бонусах](get-one-bonus.md) в массиве `items`:

```json
{"items" : [{bonus #1}, {bonus #2}, ... {bonus #n}], "has_more": true}
```