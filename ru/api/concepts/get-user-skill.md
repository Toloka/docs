# Получить значение навыка исполнителя

{% include [announce](../_includes/announce.md) %}

Получает значение навыка исполнителя.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/user-skills/<id>
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    GET ihttps://sandbox.toloka.dev/api/v1/user-skills/<id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path-параметры {#path-params}

{% include [get-user-skill-skill-user-id-table](../_includes/concepts/get-user-skill/id-get-user-skill/skill-user-id-table.md) %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

Содержит свойства навыка в формате JSON.

{% include [set-skill-user-skill-id](../_includes/concepts/set-skill/id-set-skill/user-skill-id.md) %}