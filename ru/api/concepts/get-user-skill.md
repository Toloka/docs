# Получить значение навыка исполнителя

Получает значение навыка исполнителя.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```json
  GET https://toloka.yandex.com/api/v1/user-skills/<id>
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```json
  GET ihttps://sandbox.toloka.yandex.com/api/v1/user-skills/<id>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**id** | Идентификатор навыка исполнителя, который присваивается паре «навык-исполнитель».


## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Ответ {#response}

Содержит свойства навыка в формате JSON.

{% include [set-skill-user-skill-id](../_includes/concepts/set-skill/id-set-skill/user-skill-id.md) %}


