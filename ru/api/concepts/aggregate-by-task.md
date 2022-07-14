# Агрегировать ответы на одно задание

Запускает агрегацию ответов на одно задание.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    POST https://toloka.yandex.com/api/v1/aggregated-solutions/aggregate-by-task
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Песочница

    ```bash
    POST https://sandbox.toloka.yandex.com/api/v1/aggregated-solutions/aggregate-by-task
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

```json
{
  "task_id": "afd1234d-12314a-cfd1424d-31214b",
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
||**task_id** | **string**

Идентификатор задания.||
||**pool_id** | **string**

Идентификатор пула.||
||**type** | **string**

Тип агрегации.

- `WEIGHTED_DYNAMIC_OVERLAP` — агрегация ответов в пуле с динамическим перекрытием (incremental relabeling, IRL).
- `DAWID_SKENE` — агрегация ответов в пуле без динамического перекрытия. Ключ `answer_weight_skill_id` для этого типа агрегации игнорируется.||
||**answer_weight_skill_id** | **string**

Навык, который определяет вес ответа исполнителя.||
||**fields** | **object**

Поля выходных данных, ответы на которые будут [агрегированы]({{ requester-result-aggregation }}). Для получения наилучших результатов каждое из этих полей должно иметь ограниченное количество вариантов ответа.||
||**fields.name** | **string**

Имя поля выходных данных.||
|#

## Ответ {#response}

Содержит агрегированный ответ на задание.

```json
{
  "confidence": 0.937152,
  "output_values": {
    "result": "OK"
  },
  "pool_id": "283",
  "task_id": "afd1234d-12314a-cfd1424d-31214b"
}
```

#|
||**Параметр**| **Описание**||
||**confidence** | **integer**

Уверенность в агрегированном ответе.||
||**output_values** | **object**

Поля выходных данных и агрегированный ответ.||
||**pool_id** | **string**

Идентификатор пула.||
||**task_id** | **string**

Идентификатор задания.||
|#