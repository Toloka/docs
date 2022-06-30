# Изменить перекрытие страницы

Изменяет перекрытие страницы заданий.

Вы можете задать [числовое значение](#number_overlap) или установить [бесконечное перекрытие](#infinite), чтобы выдавать страницу заданий всем исполнителям (например, для обучающих заданий).

## Запрос {#request}

{% list tabs %}
- Боевая версия

  ```json
  PATCH https://toloka.yandex.com/api/v1/task-suites/<task_suite_id>
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON

  ```

- Песочница

  ```json
  PATCH https://sandbox.toloka.yandex.com/api/v1/task-suites/<task_suite_id>
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON

  ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**task_suite_id** | Идентификатор страницы.


## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}


## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}


#|
||**Параметр**| **Описание**||
||**open_pool** | **boolean**
Открыть пул сразу после завершения операции, если пул закрыт. По умолчанию значение `false`.||
|#


## Тело запроса {#body}

#### Числовое значение перекрытия

```json
{
   "overlap": <new overlap value>,
   "infinite_overlap": false
}
```

#### Бесконечное перекрытие

```json
{
   "overlap": null,
   "infinite_overlap": true
}
```

#|
||**Параметр**| **Описание**||
||**overlap** | **integer \| обязательный при условии**

Обязателен, если при создании страницы заданий не используется параметр `allow_defaults=true` и перекрытие не указано в параметрах пула (ключ [defaults.​default_​overlap_for_​new_task_suites](pool.md#default-overlap)).
Перекрытие страницы заданий.||
||**infinite_overlap** | **boolean \| обязательный**

Выдача страницы заданий с бесконечным перекрытием. Используется, например, для страниц обучающих заданий, чтобы выдать их всем исполнителям:
- `true` — установить бесконечное перекрытие;
- `false` — оставить перекрытие, указанное для страницы заданий или пула.
||
|#

## Ответ {#response}

Содержит [страницу заданий в формате JSON](create-task-suite.md#body).

