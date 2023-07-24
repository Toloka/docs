# Получить свойства обучения

{% include [announce](../_includes/announce.md) %}

Получает свойства обучающего пула.

Идентификатор обучающего пула можно узнать из [списка обучающих пулов](get-training-list.md).

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/trainings/<training_id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/trainings/<training_id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**training_id** | Идентификатор пула.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

Содержит сведения об обучающем пуле (см. описание в разделе [Создать обучение](create-training.md#response)).