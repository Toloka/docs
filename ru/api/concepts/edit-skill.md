# Редактировать навык

Изменяет название, комментарий и уровень доступа к навыку.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    PUT https://toloka.yandex.com/api/v1/skills/<skill id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<skill parameters, including updated ones>}
    ```

- Песочница

    ```bash
    PUT https://sandbox.toloka.yandex.com/api/v1/skills/<skill id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<skill parameters, including updated ones>}
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**skill_id** | Идентификатор навыка.

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

В теле запроса укажите **все** [параметры](create-skill.md#body) навыка, включая обновляемые.

## Ответ {#response}

Содержит обновленную информацию о навыке (см. описание в разделе [Создать навык](create-skill.md#response)).