# Остановить выдачу страницы заданий

{% include [announce](../_includes/announce.md) %}

Останавливает выдачу страницы заданий исполнителям.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    PATCH https://toloka.dev/api/v1/task-suites/<task_suite_id>/set-overlap-or-min
    Authorization: ApiKey PlaceYourRealApiKey_Here
    Content-Type: application/json
    ```

- Песочница

    ```bash
    PATCH https://sandbox.toloka.dev/api/v1/task-suites/<task_suite_id>/set-overlap-or-min
    Authorization: ApiKey PlaceYourRealApiKey_Here
    Content-Type: application/json
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**task_suite_id** | Идентификатор страницы.

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

```json
{
  "overlap": 0
}
```

#|
||**Параметр**| **Описание**||
||**overlap** | **integer \| обязательный при условии**

Обязателен, если при создании страницы заданий не используется параметр `allow_defaults=true` и перекрытие не указано в параметрах пула (ключ [defaults.​default_​overlap_for_​new_task_suites](pool.md#default-overlap)).

Перекрытие страницы заданий.||
|#

## Ответ {#response}

Содержит [данные страницы заданий в формате JSON](create-task-suite.md#overlap).