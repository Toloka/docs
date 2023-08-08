# Отправить обучение в архив

{% include [announce](../_includes/announce.md) %}

Переносит обучающий пул в архив.

Если обучение не используется, его можно перенести в архив. Перед архивацией проверьте два условия:

- Обучающий пул должен быть в статусе «закрыт».

- Все основные пулы, к которым привязан обучающий пул, должны быть [отправлены в архив](archive-pool.md).

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    POST https://toloka.dev/api/v1/trainings/<training_id>/archive
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    POST https://sandbox.toloka.dev/api/v1/trainings/<training_id>/archive
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**training_id** | Идентификатор пула.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

{% note info %}

Если обучающий пул уже архивирован, при попытке повторно отправить его в архив будет возвращен пустой ответ со статусом 204.

{% endnote %}

```json
{
  "id": "95029e60-eace-4a3e-96b9-c72c5e727218",
  "type": "TRAINING.ARCHIVE",
  "status": "SUCCESS",
  "submitted": "2021-02-26T10:13:32.921",
  "started": "2021-02-26T10:13:32.921",
  "finished": "2021-02-26T10:13:32.921",
  "progress": 100,
  "parameters": {
    "training_id": "123456"
  },
  "details": {}
}
```

#|
||**Параметр**| **Описание**||
||**id** | **string**

Идентификатор исполнителя.||
||**type** | **string**

Тип операции: `TRAINING.ARCHIVE` — отправить обучение в архив.||
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
||**parameters.training_id** | **string**

Идентификатор обучающего пула.||
||**details** | **object**

Детали выполнения операции.||
|#