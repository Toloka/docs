# Переместить цепочку сообщений

{% include [announce](../_includes/announce.md) %}

Добавляет или удаляет цепочку сообщений из папки.

Цепочки сообщений, которые находятся в папке `UNREAD`, в интерфейсе отмечены как непрочитанные.

Цепочки сообщений, находящиеся в папке `IMPORTANT`, в интерфейсе отмечены как важные.

## Запрос {#request}

#### Добавить в папку

Добавляет цепочку сообщений в папку.

{% list tabs %}

- Боевая версия

    ```bash
    POST https://toloka.dev/api/v1/message-threads/<thread_id>/add-to-folders
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

- Песочница

    ```bash
    POST https://sandbox.toloka.dev/api/v1/message-threads/<thread_id>/add-to-folders
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

{% endlist %}

#### Удалить из папки

Удаляет цепочку сообщений из папки.

{% list tabs %}

- Боевая версия

    ```bash
    POST https://toloka.dev/api/v1/message-threads/<thread_id>/remove-from-folders
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

- Песочница

    ```bash
    POST https://sandbox.toloka.dev/api/v1/message-threads/<thread_id>/remove-from-folders
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
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
  "folders": ["UNREAD", "IMPORTANT"]
}
```

#|
||**Параметр**| **Описание**||
||**folders** | **array of strings**

Папки, в которые нужно добавить или из которых надо удалить цепочку сообщений.||
|#