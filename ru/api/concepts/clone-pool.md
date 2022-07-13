# Клонировать пул

Создает дубликат пула.

Будет создан пустой пул с теми же параметрами.

## Запрос {#request}

{% list tabs %}

- Песочница

    ```bash
    POST https://sandbox.toloka.yandex.com/api/v1/pools/<pool_id>/clone
    Authorization: OAuth <OAuth token>
    ```

- Боевая версия

    ```bash
    POST https://toloka.yandex.com/api/v1/pools/<pool_id>/clone
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**pool_id** | Идентификатор пула.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

```json
{
  "id" : "7ea08f99-5e24-47b4-b61f-c177a868d801",
  "type" : "POOL.CLONE",
  "status" : "SUCCESS",
  "submitted" : "2016-04-07T16:06:15.902",
  "started" : "2016-04-07T16:06:15.902",
  "finished" : "2016-04-07T16:06:15.902",
  "progress" : 100,
  "parameters" : {
    "pool_id" : "1"
  },
  "details" : {
    "pool_id" : "2"
  }
}
```

#|
||**Параметр** | **Описание**||
||**id** | **string**

Идентификатор исполнителя.||
||**type** | **string**

Тип операции: `POOL.CLONE` — клонирование пула.||
||**status** | **string**

Статус операции:

- `PENDING` — выполнение не началось;
- `RUNNING` — выполняется;
- `SUCCESS` — успешно выполнена;
- `FAIL` — не выполнена.||
||**submitted** | **string**

Дата и время отправки запроса по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**started** | **string**

Дата и время начала операции по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**finished** | **string**

Дата и время окончания операции по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**progress** | **integer**

Ход выполнения операции в процентах.||
||**parameters.pool_id** | **string**

Идентификатор исходного пула.||
||**details.pool_id** | **string**

Идентификатор нового пула.||
|#