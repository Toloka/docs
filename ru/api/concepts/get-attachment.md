# Получить метаинформацию о файле

{% include [announce](../_includes/announce.md) %}

Получает свойства прикрепленного к ответу в задании файла.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/attachments/<file_id>
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/attachments/<file_id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**file_id** | Идентификатор файла.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

Сведения о файле.

```json
{
  "id" : "0983459b-e26f-42f3-a5fd-6e3feee913e7",
  "attachment_type" : "ASSIGNMENT_ATTACHMENT",
  "name" : "ExampleAttachment.txt",
  "details" : {
    "user_id" : "ae1d5431cfc59e25b4abbbe75666d59b",
    "assignment_id" : "5241f238-6640-43e4-80bb-3283893cd221",
    "pool_id" : "154"
  },
  "created" : "2016-05-25T16:14:27.748",
  "media_type" : "application/octet-stream"
}
```

#|
||**Параметр**| **Описание**||
||**id** | **string**

Идентификатор файла.||
||**attachment_type** | **string**

Тип приложения. На данный момент ключ имеет одно значение — `ASSIGNMENT_ATTACHMENT`.||
||**name** | **string**

Имя файла.||
||**details** | **object**

Информация о пуле, задании и исполнителе, от которого получен файл.||
||**details.user_id** | **string**

Идентификатор исполнителя, от которого получен файл.||
||**details.assignment_id** | **string**

Идентификатор выдачи страницы заданий исполнителю.||
||**details.pool_id** | **string**

Идентификатор пула.||
||**created** | **string**

Дата загрузки файла в Толоку.||
||**media_type** | **string**

MIME-тип данных.||
|#