# Клонировать обучение

Создает дубликат обучающего пула.

Будет создан пустой обучающий пул с теми же параметрами.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  POST https://toloka.yandex.com/api/v1/training/<training_id>/clone
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  POST https://sandbox.toloka.yandex.com/api/v1/training/<training_id>/clone
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**training_id** | Идентификатор пула.


## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Ответ {#response}

```json
{
  "id": "7ea08f99-5e24-47b4-b61f-c177a868d801",
  "type": "TRAINING.CLONE",
  "status": "SUCCESS",
  "submitted": "2021-02-26T10:13:32.921",
  "started": "2021-02-26T10:13:32.921",
  "finished": "2021-02-26T10:13:32.921",
  "progress": 100,
  "parameters": {
    "training_id": "123456"
  },
  "details": {
    "training_id": "123457"
  }
}
```

#|
||**Параметр**| **Описание**||
||**id** | **string**

Идентификатор исполнителя.||
||**type** | **string**
Тип операции: `TRAINING.CLONE` — клонировать обучение.||
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
||**parameters.training_id** | **string**
Идентификатор исходного обучающего пула.||
||**details.training_id** | **string**
Идентификатор нового обучающего пула.||
|#
