# Редактировать навык

{% include [announce](../_includes/announce.md) %}

Изменяет название, комментарий и уровень доступа к навыку.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    PUT https://toloka.dev/api/v1/skills/<id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    Content-Type: application/json

    {<skill parameters, including updated ones>}
    ```

- Песочница

    ```bash
    PUT https://sandbox.toloka.dev/api/v1/skills/<id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    Content-Type: application/json

    {<skill parameters, including updated ones>}
    ```

{% endlist %}

## Path-параметры {#path-params}

{% include [edit-skill-skill-id-table](../_includes/concepts/edit-skill/id-edit-skill/skill-id-table.md) %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

В теле запроса укажите **все** [параметры](create-skill.md#body) навыка, включая обновляемые.

## Ответ {#response}

Содержит обновленную информацию о навыке (см. описание в разделе [Создать навык](create-skill.md#response)).