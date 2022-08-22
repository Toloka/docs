# Ответить на цепочку сообщений

{% include [announce](../_includes/announce.md) %}

Отвечает на цепочку сообщений.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    POST https://toloka.dev/api/v1/message-threads/<thread_id>/reply
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Песочница

    ```bash
    POST https://sandbox.toloka.dev/api/v1/message-threads/<thread_id>/reply
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**thread_id** | Идентификатор цепочки сообщений.

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

```json
{
  "text": {
    "EN": "Thank you!"
  }
}
```

#|
||**Параметр**| **Описание**||
||**text** | **string**
Текст сообщения. Можно привести текст на нескольких языках (сообщение придет на языке исполнителя). Формат: `"<язык RU/EN/TR/ID/FR>": "<текст сообщения>"`.||
|#