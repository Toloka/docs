# Разблокировать доступ

{% include [announce](../_includes/announce.md) %}

Удаляет блокировку.

## Запрос {#query-params}

{% list tabs %}

- Боевая версия

    ```bash
    DELETE https://toloka.dev/api/v1/user-restrictions/<ban_id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    DELETE https://sandbox.toloka.dev/api/v1/user-restrictions/<ban_id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**ban_id** | Идентификатор блокировки.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}