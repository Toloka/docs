# Остановить выдачу задания

Останавливает выдачу задания исполнителям.

В поле `overlap` укажите значение `0`. Для заданий с бесконечным перекрытием измените значение в поле `infinite_overlap` на `false`.

## Запрос {#request}

{% list tabs %}

- Песочница

  ```json
  PATCH https://sandbox.toloka.yandex.com/api/v1/tasks/<task_id>/set-overlap-or-min
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

- Боевая версия

  ```json
  PATCH https://toloka.yandex.com/api/v1/tasks/<task_id>/set-overlap-or-min
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
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

