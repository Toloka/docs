# Редактировать обучение

{% include [announce](../_includes/announce.md) %}

Вносит изменения в обучающий пул.

{% note info %}

О редактировании обычного пула читайте в разделе [Редактировать пул](edit-pool.md).

{% endnote %}

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    PUT https://toloka.dev/api/v1/trainings/<training_id>
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json

    {<training parameters, including updated ones>}
    ```

- Песочница

    ```bash
    PUT https://sandbox.toloka.dev/api/v1/trainings/<training_id>
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json

    {<training parameters, including updated ones>}
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**training_id** | Идентификатор пула.

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

В теле запроса укажите **все** [параметры](create-training.md#training-param) обучения, включая обновляемые.

## Ответ {#response}

Содержит сведения об измененном обучающем пуле (см. описание в разделе [Создать обучение](create-training.md#response)).