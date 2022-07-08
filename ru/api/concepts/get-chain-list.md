# Получить список цепочек сообщений

Получает список цепочек сообщений.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/message-threads
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/message-threads
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}


#|
||**Параметр**|**Описание**||
||**folder** | **string**

{% include [messages-folder-list](../_includes/concepts/message-send/id-messages/folder-list.md) %}||
||**folder_ne** | **string**
Папки, в которых не искать цепочку. Можно указать несколько значений через запятую.||
||**sort** | **string**

Параметры для сортировки:
- `id` — идентификатор страницы заданий;
- `created` — дата создания страницы заданий по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.

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
