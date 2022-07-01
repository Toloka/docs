# Удалить навык у исполнителя

Удаляет навык у исполнителя.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  DELETE https://toloka.yandex.com/api/v1/user-skills/<id>
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  DELETE https://sandbox.toloka.yandex.com/api/v1/user-skills/<id>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Path-параметры {#path-params}

{% include [get-user-skill-skill-user-id-table](../_includes/concepts/get-user-skill/id-get-user-skill/skill-user-id-table.md) %}


## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}
