# Отправить пул в архив

Переносит пул в архив.

Если пул не используется, его можно перенести в архив. Пул должен быть в статусе <q>закрыт</q>.

Пул с отклоненными заданиями можно заархивировать через 9 дней с момента последнего отклонения. Этот период необходим для того, чтобы пересмотреть результаты, если исполнитель подал апелляцию.

Экзамены с автоматической приемкой по точности, в которых отклоняются задания с недостаточной точностью, тоже можно заархивировать через 9 дней.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```json
  POST https://toloka.yandex.com/api/v1/pools/<pool_id>/archive
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```json
  POST https://sandbox.toloka.yandex.com/api/v1/pools/<pool_id>/archive
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

Если пул уже архивирован, при попытке повторно отправить его в архив будет возвращен пустой ответ со статусом 204.

{% endnote %}


Содержит сведения о выполнении операции.

```json
{
  "id" : "57068577e4b0bf7b07a0256f",
  "type" : "POOL.ARCHIVE",
  "status" : "SUCCESS",
  "submitted" : "2016-04-07T16:06:15.902",
  "started" : "2016-04-07T16:06:15.902",
  "finished" : "2016-04-07T16:06:15.902",
  "progress" : 100,
  "parameters" : {
    "pool_id" : "1"
  }
}
```
#|
||Параметр | Описание||
||**id** | **string**

Идентификатор исполнителя.||
||**type** | **string**

Тип операции: `POOL.ARCHIVE` — отправка пула в архив.||
||**status** | **string**

Статус операции:
- `PENDING` — выполнение не началось;
- `RUNNING` — выполняется;
- `SUCCESS` — успешно выполнена;
- `FAIL` — не выполнена.||
||**submitted** | **string**

Дата и время отправки запроса по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
||**started** | **string**

Дата и время начала операции по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
||**finished** | **string**
Дата и время окончания операции по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
||**progress** | **integer**
Ход выполнения операции в процентах.||
||**parameters.pool_id** | **string**
Идентификатор пула.||
|#


