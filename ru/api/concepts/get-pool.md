# Получить свойства пула

Получает свойства пула.

Идентификатор пула можно узнать из [списка пулов](get-pool-list.md).

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.yandex.com/api/v1/pools/<pool_id>
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.yandex.com/api/v1/pools/<pool_id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**pool_id** | Идентификатор пула.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

Содержит параметры пула (см. описание в разделе [Создать пул](create-pool.md#response)).