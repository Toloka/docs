# Удалить подписку

{% include [announce](../_includes/announce.md) %}

Удаляет подписку.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    DELETE https://toloka.dev/api/v1/webhook-subscriptions/<subscription_id>
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    DELETE https://sandbox.toloka.dev/api/v1/webhook-subscriptions/<subscription_id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**subscription_id** | Идентификатор подписки.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

Если запрос выполнен успешно, сервер возвращает HTTP-статус выполнения операции: «204 No Content» или «404 Not Found».