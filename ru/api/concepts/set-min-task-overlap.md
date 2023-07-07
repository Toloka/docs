# Остановить выдачу задания

{% include [announce](../_includes/announce.md) %}

Останавливает выдачу задания исполнителям.

В поле `overlap` укажите значение `0`. Для заданий с бесконечным перекрытием измените значение в поле `infinite_overlap` на `false`.

## Запрос {#request}

{% list tabs %}

- Песочница

    ```bash
    PATCH https://sandbox.toloka.dev/api/v1/tasks/<task_id>/set-overlap-or-min
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

- Боевая версия

    ```bash
    PATCH https://toloka.dev/api/v1/tasks/<task_id>/set-overlap-or-min
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**task_id** | Идентификатор задания.

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

```json
{
  "overlap": 0,
  "infinite_overlap": false
}
```

## Ответ {#response}

Содержит [данные задания в формате JSON](create-task.md#body).