# Разблокировать доступ

Удаляет блокировку.

## Запрос {#query-params}

{% list tabs %}

- Боевая версия

    ```bash
    DELETE https://toloka.yandex.com/api/v1/user-restrictions/<ban_id>
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    DELETE https://sandbox.toloka.yandex.com/api/v1/user-restrictions/<ban_id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**ban_id** | Идентификатор блокировки.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}