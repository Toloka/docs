# Закрыть пул для редактирования

{% include [announce](../_includes/announce.md) %}

Закрывает пул для редактирования.

Чтобы внести изменения в пул, закройте его для редактирования.

{% note info %}

Если после редактирования не открыть пул вручную, он откроется автоматически через 15 минут.

В этом случае не производятся проверки, способные заблокировать открытие пула.

{% endnote %}

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    POST https://toloka.dev/api/v1/pools/<pool_id>/close-for-update
    Authorization: OAuth <OAuth token>
    ```

- Песочница

    ```bash
    POST https://sandbox.toloka.dev/api/v1/pools/<pool_id>/close-for-update
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

{% note info %}

Если текущий статус пула совпадает с запрашиваемым, возвращается пустой ответ со статусом 204.

{% endnote %}

```json
{
  "id": "019587fd-b536-49f8-b6dc-01ffc25f8594",
  "type": "POOL.CLOSE",
  "status": "PENDING",
  "submitted": "2021-11-24T07:47:50.120",
  "started" : "2021-11-24T07:47:50.120",
  "finished" : "2021-11-24T07:47:50.120",
  "progress" : 100,
  "parameters": {
    "pool_id": "21"
  }
}
```

#|
||**Параметр** | **Описание**||
||**id** | **string**

Идентификатор исполнителя.||
||**type** | **string**

Тип операции: `POOL.CLOSE` — закрытие пула.||
||**status** | **string**

Статус операции:

- `PENDING` — выполнение не началось;
- `RUNNING` — выполняется;
- `SUCCESS` — успешно выполнена;
- `FAIL` — не выполнена.
||
||**submitted** | **string**

Дата и время отправки запроса по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**started** | **string**

Дата и время начала операции по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**finished** | **string**

Дата и время окончания операции по UTC в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**progress** | **integer**

Ход выполнения операции в процентах.||
||**parameters.pool_id** | **string**

Идентификатор пула.||
|#