# Получить список файлов

Получает список сохраненных в Толоке файлов.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.yandex.com/api/v1/attachments
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.yandex.com/api/v1/attachments
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

Идентификатор пула.||
||**assignment_id** | **string**

Идентификатор выдачи страницы заданий.||
||**name** | **string**

Имя файла.||
||**type** | **string**

Тип приложения. На данный момент ключ имеет одно значение — `ASSIGNMENT_ATTACHMENT`.||
||**user_id** | **string**

Идентификатор исполнителя, который отправил файл(ы).||
||**sort** | **string**

Параметры для сортировки:

- `id` — идентификатор файла;
- `created` — дата отправки файла по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.

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

Можно настроить показ списка файлов частями (например, по 10 файлов):

1. Показать первые 10 файлов, начиная с бонуса с наименьшим идентификатором.
1. Показывать оставшиеся файлы по 10 штук в порядке возрастания.

**Показать первые 10 бонусов**

{% list tabs %}
- Боевая версия

    ```bash
    GET https://toloka.yandex.com/api/v1/attachments?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.yandex.com/api/v1/attachments?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

**Показывать остальные части с сортировкой по возрастанию идентификатора**

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.yandex.com/api/v1/attachments?sort=id&limit=10&id_gt=<ID of the last file from the previous response>
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.yandex.com/api/v1/attachments?sort=id&limit=10&id_gt=<ID of the last file from the previous response>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Ответ {#response}

[Сведения о файлах](get-attachment.md) в массиве `items`:

```json
{"items" : [{file #1}, {file #2}, ... {file #n}], "has_more": false}
```