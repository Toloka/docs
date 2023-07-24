# Получить лог операции

{% include [announce](../_includes/announce.md) %}

Получает лог операции.

Логи можно получить для асинхронных операций (`async_mode = true`). Такие операции выполняются в фоновом режиме.

Логи доступны только за последний месяц. Чтобы получить логи за более ранний период, обратитесь в [службу поддержки](../../guide/troubleshooting/support.md).

Лог операции можно получить при:

- создании [одного или нескольких](create-task.md) заданий;
- создании [одной или нескольких](create-task-suite.md) страниц заданий;
- [выдаче бонусов](create-bonus.md) исполнителям.

При успешной операции лог содержит `id` созданных объектов, а при неуспешной — сведения об ошибках валидации.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/operations/<operation_id>/log
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/operations/<operation_id>/log
    Authorization: ApiKey PlaceYourRealApiKey_Here
    ```

{% endlist %}
## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**operation_id** | Идентификатор операции.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Ответ {#response}

Содержит JSON-массив с описанием каждого шага операции.

```json
[
  {
    "type": <action type>,
    "success": <true/false>,
    "input": {
      <input values at the operation step>
    },
    "output": {
      <output values at the operation step or error details>
    }
  },
  ...
]
```

#|
||**Параметр**| **Описание**||
||**type** | **string**

Тип действия на шаге операции. Зависит от:

- типа операции, по которой запрашивается лог;
- результата выполнения (`success: true/false`).

Значения `type` при успешной асинхронной операции:

- `USER_BONUS_PERSIST` — выдача бонуса.
- `TASK_CREATE` — создание задания.
- `TASK_SUITE_CREATE` — создание страницы заданий.
Значения `type` при неуспешной асинхронной операции:
- `USER_BONUS_VALIDATE` — выдача бонуса.
- `TASK_VALIDATE` — создание задания.
- `TASK_SUITE_VALIDATE` — создание страницы заданий.

От типа операции зависят значения `input` и `output`.||
||**success** | **boolean**

Результат выполнения шага:

- `true` — действие выполнено успешно;
- `false` — действие не выполнено.||
||**input** | **JSON**

Данные в `input` дублируют переданные при создании операции входные данные.||
||**output** | **JSON**

Выходные данные шага операции.

Данные в `output` при успешной операции:

- Для действия `USER_BONUS_PERSIST` — `user_bonus_id` (`id` выданного бонуса).
- Для действия `TASK_CREATE` — `task_id` (`id` созданного задания).
- Для действия `TASK_SUITE_CREATE` — `task_suite_id` (`id` созданной страницы заданий).

Данные в `output` при неуспешной операции:

- `code` — имя ошибки.
- `message` — пояснение, как исправить ошибку.
- `payload` — при `code = VALIDATION_ERROR` уточняет причину ошибки.||
|#

{% cut "Пример лога при успешной выдаче бонусов" %}

```json
[
  {
    "type": "USER_BONUS_PERSIST",
    "success": true,
    "input": {
      "id": 65,
      "amount": 1.5,
      "created": "2021-02-02T12:51:00",
      "user_id": "ec00d2407f7241258d0faba610110d95",
      "public_title": {
        "EN": "Good job!",
        "RU": "Молодец!"
      },
      "public_message": {
        "EN": "Ten tasks completed",
        "RU": "Выполнено 10 заданий"
      },
      "private_comment": "pool_123456",
      "without_message": false
    },
    "output": {
      "user_bonus_id": "2128"
    }
  }
]
```

{% endcut %}

{% cut "Пример лога при неуспешной выдаче бонусов" %}

```json
[
  {
    "type": "USER_BONUS_VALIDATE",
    "success": false,
    "input": {
      "id": 65,
      "amount": 1.5,
      "created": "2021-02-02T12:51:00",
      "user_id": "ec00d2407f7241258d0faba610110d95",
      "public_title": {
        "EN": "Good job!",
        "RU": "Молодец!"
      },
      "public_message": {
        "EN": "Ten tasks completed",
        "RU": "Выполнено 10 заданий"
      },
      "private_comment": "pool_123456",
      "without_message": false
   },
    "output": {
      "user_id": {
        "code": "ENTITY_DOES_NOT_EXIST",
        "message": "Entity does not exist"
      }
    }
  }
]
```

{% endcut %}