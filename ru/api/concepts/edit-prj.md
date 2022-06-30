# Редактировать проект

Редактирует проект.

В теле запроса укажите **все** параметры обновляемого проекта. Идентификатор проекта можно узнать из [списка проектов](get-prj-list.md).

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```json
  PUT https://toloka.yandex.com/api/v1/projects/<project_id>
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON

  {<project parameters, including updated ones>}
  ```

- Песочница

  ```json
  PUT https://sandbox.toloka.yandex.com/api/v1/projects/<project_id>
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON

  {<project parameters, including updated ones>}
  ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**project_id** | Идентификатор проекта.


## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}


## Ответ {#response}

Содержит обновленную информацию о проекте в формате JSON (см. [пример проекта](create-prj.md#body)).

