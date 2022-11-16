# Агрегировать ответы в пуле

{% include [announce](../_includes/announce.md) %}

Запускает агрегацию ответов на все выполненные задания в пуле.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    POST https://toloka.dev/api/v1/aggregated-solutions/aggregate-by-pool
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Песочница

    ```bash
    POST https://sandbox.toloka.dev/api/v1/aggregated-solutions/aggregate-by-pool
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

```json
{
  "pool_id": "283",
  "type": "WEIGHTED_DYNAMIC_OVERLAP",
  "answer_weight_skill_id": "1289",
  "fields": [
    {
      "name": "result"
    }
  ]
}
```

#|
||**Параметр**| **Описание**||
||**pool_id** | **string**

Идентификатор пула.||
||**type** | **string**

Способ агрегации результатов:

- `WEIGHTED_DYNAMIC_OVERLAP` — агрегация ответов в пуле на основе навыка исполнителя.
- `DAWID_SKENE` — агрегация ответов в пуле без динамического перекрытия. Ключ `answer_weight_skill_id` для этого типа агрегации игнорируется.||
||**answer_weight_skill_id** | **string**

Навык, который определяет вес ответа исполнителя.

Обязателен, если выбран тип агрегации `WEIGHTED_DYNAMIC_OVERLAP`.||
||**fields** | **object**

Поля выходных данных, ответы на которые будут [агрегированы](../../guide/concepts/result-aggregation.md). Для получения наилучших результатов каждое из этих полей должно иметь ограниченное количество вариантов ответа.

Если выбран тип агрегации `DAWID_SKENE`, то можно указать только одно значение.||
||**fields.name** | **string**

Имя поля выходных данных.||
|#

## Ответ {#response}

Содержит сведения об операции. Проверяйте [статус операции](operations.md). После ее завершения [получите результаты агрегации](get-aggregated-result.md).

```json
{
  "id": "fadfe3jk-fdafue2-fda32890-fdafdi23",
  "type": "SOLUTION.AGGREGATE",
  "status": "PEDNDING",
  "submitted": "2018-22-10T14:18:35",
  "progress" : 0,
  "parameters": {
    "pool_id": "283"
  }
}
```

#|
||**Параметр**| **Описание**||
||**id** | **string**

Идентификатор операции.||
||**type** | **string**

Тип операции:

- `POOL.OPEN` — открытие пула.
- `POOL.CLOSE` — закрытие пула.
- `PROJECT.ARCHIVE` — отправка проекта в архив.
- `POOL.ARCHIVE` — отправка пула в архив.
- `SOLUTION.AGGREGATE` — агрегация ответов.
- `TASK_SUITE.BATCH_CREATE` — создание нескольких страниц заданий.||
||**status** | **string**

Статус операции:

- `PENDING` — выполнение не началось;
- `RUNNING` — выполняется;
- `SUCCESS` — успешно выполнена;
- `FAIL` — не выполнена.||
||**submitted** | **string**

Дата и время отправки запроса по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**progress** | **integer**

Ход выполнения операции в процентах.||
||**parameters** | **object**

Параметры операции в запросе.||
|#