# Получить список навыков исполнителя

Получает список навыков исполнителя.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```json
  GET https://toloka.yandex.com/api/v1/user-skills
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```json
  GET https://sandbox.toloka.yandex.com/api/v1/user-skills
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}


#|
||**Параметр** | **Описание**||
||**user_id** | **string**

Идентификатор исполнителя.||
||**skill_id** | **string**

Идентификатор навыка.||
||**sort** | **string**

Параметры для сортировки:
- `id` — идентификатора навыка;
- `created` — дата создания навыка по UTC в формате YYYY-MM-DD;
- `modified` — дата изменения навыка по UTC в формате YYYY-MM-DD.

{% include [get-tasks-list-about-sorting](../_includes/concepts/get-tasks-list/id-get-tasks-list/about-sorting.md) %}
||
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

  ```json
  GET https://toloka.yandex.com/api/v1/user-skills?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```json
  GET https://sandbox.toloka.yandex.com/api/v1/user-skills?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

**Показывать остальные части с сортировкой по возрастанию идентификатора**

{% list tabs %}

- Боевая версия

  ```json
  GET https://toloka.yandex.com/api/v1/skills?sort=id&limit=10&id_gt=<ID of the last skill from the previous response>
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```json
  GET https://sandbox.toloka.yandex.com/api/v1/skills?sort=id&limit=10&id_gt=<ID of the last skill from the previous response>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Ответ {#response}

[Свойства навыков исполнителей](get-user-skill.md) в массиве `items`:

```json
{"items" : [{<user skill 1>}, {<user skill 2>}, ... {<user skill n>}], "has_more": false}
```

