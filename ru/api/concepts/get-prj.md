# Получить свойства проекта

{% include [announce](../_includes/announce.md) %}

Получает свойства проекта.

Идентификатор проекта можно узнать из [списка проектов](get-prj-list.md).

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/projects/<project_id>
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/projects/<project_id>
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**project_id** | Идентификатор проекта.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

Содержит свойства проекта в формате JSON (см. [пример проекта](create-prj.md#body)).