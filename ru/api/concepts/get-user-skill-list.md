# Получить список исполнителей с назначенными навыками

{% include [announce](../_includes/announce.md) %}

Получает список исполнителей с назначенными навыками. Используя [query-параметры](#query-params), вы можете отфильтровать данные в ответе, например:

- Получить список всех исполнителей с определенным навыком с помощью query-параметра `skill_id`:

   ```bash
   GET https://toloka.dev/api/v1/user-skills?skill_id=<skill_id>
   ```

- Получить список всех навыков определенного исполнителя с помощью query-параметра `user_id`:

   ```bash
   GET https://toloka.dev/api/v1/user-skills?user_id=<user_id>
   ```

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/user-skills
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-skills
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}

#|
||**Параметр** | **Описание**||
||**user_id** | **string**

Идентификатор исполнителя. Позволяет получить список навыков определенного исполнителя.||
||**skill_id** | **string**

Идентификатор навыка. Позволяет получить список исполнителей с определенным навыком.||
||**sort** | **string**

Параметры для сортировки:

- `id` — идентификатора навыка;
- `created` — дата создания навыка по UTC в формате YYYY-MM-DD;
- `modified` — дата изменения навыка по UTC в формате YYYY-MM-DD.

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
- **modified_gt** (**string** — объекты, измененные после указанной даты)
- **modified_gte** (**string** — объекты, измененные после указанной даты включительно)
- **modified_lt** (**string** — объекты, измененные до указанной даты)
- **modified_lte** (**string** — объекты, измененные до указанной даты включительно)||
|#

## Пример запроса {#request-example}

Можно настроить показ списка навыков частями (например, по 10 навыков):

1. Показать первые 10 навыков, начиная с навыка с наименьшим идентификатором.
1. Показывать оставшиеся навыков по 10 штук в порядке возрастания.

**Показать первые 10 навыков**

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/user-skills?sort=id&limit=10
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-skills?sort=id&limit=10
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

**Показывать остальные части с сортировкой по возрастанию идентификатора**

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/skills?sort=id&limit=10&id_gt=<ID of the last skill from the previous response>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/skills?sort=id&limit=10&id_gt=<ID of the last skill from the previous response>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

## Ответ {#response}

[Свойства навыков исполнителей](get-user-skill.md#response) в массиве `items`:

```json
{"items" : [{<user 1 skill 1 >}, {<user 1 skill 2>}, ... {<user 1 skill n>}, ... {<user n skill 1>}, {<user n skill 2>}, ... {<user n skill n>}], "has_more": false}
```