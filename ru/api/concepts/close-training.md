# Закрыть обучение

{% include [announce](../_includes/announce.md) %}

Закрывает обучающий пул.

Чтобы перестать раздавать обучающие задания исполнителям, закройте обучающий пул.

В результате запросов создается операция. Чтобы отслеживать ход операции, отправьте запрос к ресурсу `/operations`.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    POST https://toloka.dev/api/v1/trainings/<training_id>/close
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

- Песочница

    ```bash
    POST https://sandbox.toloka.dev/api/v1/trainings/<training_id>/close
    Authorization: OAuth PlaceYourRealOAuthToken_Here
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

Если текущий статус обучающего пула совпадает с запрашиваемым, то возвращается пустой ответ со статусом 204.

{% endnote %}

```json
{
  "id": "52829015-033f-4c3a-a7cc-0d7eff235663",
  "type": "TRAINING.CLOSE",
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

Тип операции: `TRAINING.CLOSE` — закрыть обучение.||
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