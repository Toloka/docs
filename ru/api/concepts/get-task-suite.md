# Получить страницу заданий

Получает страницу заданий.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```json
  GET https://toloka.yandex.com/api/v1/task-suites/<task_suite_id>
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```json
  GET https://sandbox.toloka.yandex.com/api/v1/task-suites/<task_suite_id>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**task_suite_id** | Идентификатор страницы.


## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Ответ {#response}

Содержит [страницу заданий в формате JSON](create-task-suite.md#body).

