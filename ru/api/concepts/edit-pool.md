# Редактировать пул

{% include [announce](../_includes/announce.md) %}

Вносит изменения в пул.

Пул нельзя редактировать, если он открыт. [Закройте пул](close-pool-for-update.md) для редактирования перед внесением изменений.

{% note info %}

О редактировании обучающего пула читайте в разделе [Редактировать обучение](edit-training.md).

{% endnote %}

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    PUT https://toloka.dev/api/v1/pools/<pool_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<pool parameters, including updated ones>}
    ```

- Песочница

    ```bash
    PUT https://sandbox.toloka.dev/api/v1/pools/<pool_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<pool parameters, including updated ones>}
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**pool_id** | Идентификатор пула.

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

В теле запроса укажите **все** [параметры](create-pool.md#pool-param) пула, включая обновляемые.

## Ответ {#response}

Содержит обновленную информацию о пуле (см. описание в разделе [Создать пул](create-pool.md#response)).