# Создать одну или несколько страниц заданий

Создает одну или несколько страниц заданий.

{% note alert %}

Вы можете отправить не более 100 000 заданий в минуту и не более 2 000 000 в день.

{% endnote %}


## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  POST https://toloka.yandex.com/api/v1/task-suites
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON

  // одна страница заданий
  {task suite parameters}

  // или несколько страниц заданий
  [{task suite 1}, {task suite 2},... {task suite N}]
  ```

- Песочница

  ```bash
  POST https://sandbox.toloka.yandex.com/api/v1/task-suites
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON

  // одна страница заданий
  {task suite parameters}

  // или несколько страниц заданий
  [{task suite 1}, {task suite 2},... {task suite N}]
  ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}


## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}


#|
||**Параметр**| **Описание**||
||**async_mode** | **boolean**

Способ обработки запроса:
- `true` — отложенный. В результате запроса создается асинхронная операция, выполняемая в фоновом режиме. Ответ содержит сведения об операции (время начала и окончания, статус).
- `false` — синхронный. Ответ содержит сведения об одной или о нескольких созданных страницах заданий.
По умолчанию значение `false`.||
||**allow_defaults** | **boolean**
Настройки перекрытия:
- `true` — использовать перекрытие, указанное в параметрах пула (ключ [defaults.default_overlap_for_new_task_suites](create-pool.md#default-overlap)).
- `false` — использовать перекрытие, указанное в параметрах страниц заданий (поле [overlap](create-task-suite.md#overlap)).
По умолчанию значение `false`.||
||**skip_invalid_items** | **boolean**

Параметры валидации JSON-объектов:
- `true` — создать страницы заданий, прошедшие валидацию.
- `false` — остановить операцию и не создавать страницы заданий, если хотя бы одна из них не прошла валидацию.
По умолчанию значение `false`.||
||**open_pool** | **boolean**

Открыть пул сразу после завершения операции, если пул закрыт. По умолчанию значение `false`.||
||**operation_id** | **string**

Идентификатор операции для отложенной загрузки одной или нескольких страниц заданий (при значении `async_mode=true`).
Рекомендуется задавать идентификатор в POST-запросе, чтобы избежать случайных ошибок. Например, повторного создания операции с теми же страницами заданий.
Идентификатор должен соответствовать [стандарту RFC4122]({{ rfc4122 }}).
В дальнейшем идентификатор можно использовать для [получения данных об операции](operations.md).||
|#


## Тело запроса {#body}

```json
{
    "id": "63614047-38c3-4ad4-8a86-99c5c651a9b8",
    "pool_id": "1",
    "tasks": [
        {"id": "49a333ea-2728-4c1c-ab1f-8ab1bfe4ee7e",
         "origin_task_id": "e3da7fe1-828d-4d9c-b49d-42c0eb5fcfde",
         "input_values": {
                "image_url": "www.image1.ru"
            },
            "known_solutions": [
                {
                    "correctness_weight": 0.95,
                    "output_values": {
                        "colour": "black"
                    }
                },
                {
                    "correctness_weight": 0.7,
                    "output_values": {
                        "colour": "gray"
                    }
                }
            ],
            "message_on_unknown_solution": "The elephant is black"
        },
        {
            "input_values": {
                "image_url": "www.image2.ru"
            },
            "known_solutions": [
                {
                    "correctness_weight": 1,
                    "output_values": {
                        "colour": "white"
                    }
                }
            ],
            "message_on_unknown_solution": "The elephant is white"
        }
    ],
    "overlap": 5,
    "infinite_overlap": false,
    "remaining_overlap": 3,
    "reserved_for": [],
    "unavailable_for": [],
    "issuing_order_override": 3,
    "mixed": true,
    "automerged": false,
    "created": "2016-04-18T12:43:04.988"
}

```

#|
||**Параметр**| **Описание**||
||**pool_id** | **string \| обязательный**

Идентификатор пула, в который загружаются задания.||
||**tasks[]** | **array of object \| обязательный**

Данные заданий.||
||**tasks[].input_values** | **object \| обязательный**

Входные данные для задания. Список пар:
```json
 "<ID of field 1>": "<value of field 1>",
 "<ID of field 2>": "<value of field 2>",
 ...
 "<ID of field N>": "<value of field N>"
```
||
||**overlap** | **integer \| обязательный при условии**

Обязателен, если при создании страницы заданий не используется параметр `allow_defaults=true` и перекрытие не указано в параметрах пула (ключ [defaults.​default_​overlap_for_​new_task_suites](pool.md#default-overlap)).
Перекрытие страницы заданий.||
||**longitude** | **float \| обязательный при условии**

Обязателен, если задания выбираются на карте. Иначе не используется.
Долгота точки на карте для страницы заданий.||
||**latitude** | **float \| обязательный при условии**

Обязателен, если задания выбираются на карте. Иначе не используется.
Широта точки на карте для страницы заданий.||
||**tasks[].known_solutions** | **object**

Ответы и подсказки для контрольных и тренировочных заданий.||
||**tasks[].known_solutions.output_values** | **object**

Правильные ответы в задании (для контрольных заданий). Если есть несколько правильных вариантов ответа, для каждого варианта нужно определить `output_values` и привести вес правильного ответа (ключ `correctness_weight`).
```json
 "<ID of field 1>": "<correct response>",
 "<ID of field 2>": "<correct response>",
 ...
 "<ID of field N>": "<correct response N>"
```
||
||**tasks[].known_solutions.correctness_weight** | **float**

Вес правильного ответа. Позволяет задать несколько вариантов правильных ответов и ранжировать их по правильности. Например, при весе правильного ответа 0.5 исполнителю засчитывается половина ошибки. Чем правильнее ответ в `correctValues`, тем выше его вес.||
||**tasks[].message_on_unknown_solution** | **string**

Подсказка к заданию (для тренировочных заданий).||
||**infinite_overlap** | **boolean \| обязательный**

Выдача страницы заданий с бесконечным перекрытием. Используется, например, для страниц обучающих заданий, чтобы выдать их всем исполнителям:
- `true` — установить бесконечное перекрытие;
- `false` — оставить перекрытие, указанное для страницы заданий или пула.||
||**reserved_for[]** | **array of integer**

Идентификаторы исполнителей, которым будет доступна страница.||
||**unavailable_for[]** | **array of integer**

Идентификаторы исполнителей, для которых страница должна быть недоступна.
||**issuing_order_override** | **float**

Приоритет страницы заданий среди других страниц в пуле. Определяет порядок выдачи
 страниц исполнителям. Чем больше значение параметра, тем выше приоритет.
 Параметр можно использовать, если в пуле `issue_task_suites_in_creation_order: true`.
 Возможные значения: от `-99999.99999` до `99999.99999`.
 По умолчанию значение `0`.
||**mixed** | **boolean**

Способ создания страницы заданий:
- `true` — автоматически с помощью опции «умное смешивание» (см. подробнее в документе [Руководство заказчика]({{ requester-task-upload }));
- — вручную.||
|#


## Ответ {#response}

{% cut "Одна страница заданий" %}

Включает:

- [данные страницы заданий](create-task-suite.md#body) в формате JSON;
- параметры, которые присваиваются автоматически:

#|
||**Параметр**| **Описание**||
||**id** | **string**

Идентификатор страницы заданий.||
||**tasks[].id** | **string**

Идентификатор задания, если страница сформирована автоматически с помощью опции «умное смешивание» (см. подробнее в документе [Руководство заказчика]({{ requester-task-upload }})).||
||**tasks[].origin_task_id** | **string**

Идентификатор задания из другого пула, с которого было скопировано это задание, для проверки мнением большинства.||
||**remaining_overlap** | **integer**

Оставшееся перекрытие для каждого задания. Например, если для задания установлено перекрытие `5`, а его разметили два человека, то значение `remaining_overlap` будет `3`.
Если задание ожидает приемки или активно, ключ принимает значение `0`.||
||**automerged** | **boolean**

Флаг страницы заданий, созданной после [слияния заданий](create-prj.md#task-merge). Значение:
- `true` — страница заданий сгенерирована в результате слияния идентичных заданий;
- `false` — обычная страница заданий, созданная «умным смешиванием» или заказчиком.||
||**created** | **string**

Дата и время создания страницы заданий по UTC в формате ISO 8601 YYYY-MM-DDThh:mm:ss[.sss].||
|#

{% endcut %}

{% cut "Несколько страниц заданий" %}

Формат ответа зависит от значения query-параметра **async_mode**:

#|
||**async_mode** | **boolean**

Способ обработки запроса:
- `true` — отложенный. В результате запроса создается асинхронная операция, выполняемая в фоновом режиме. Ответ содержит сведения об операции (время начала и окончания, статус).
- `false` — синхронный. Ответ содержит сведения об одной или о нескольких созданных страницах заданий.

По умолчанию значение `false`.||
|#

{% list tabs %}

- Страницы заданий (async_mode=false)

  ```json
  {
    "items": {
      "0": {<task suite>},
      "2": {<task suite>}, ...
      "<n>": {<task suite N>}
    },
    "validation_errors": {
      "1": {<validation errors for the task suite>},
      "3": {<validation errors for the task suite>}, ...
      "<n>": {<validation errors for task suite N>}
    }
  }
  ```
  #|
  ||**Параметр** |**Описание**||
  ||**items** | **object**

  Объект с созданными страницами заданий.||
  ||**validation_errors** | **object**

  Объект с ошибками на страницах заданий. Возвращается, если в запросе используется параметр `skip_invalid_items=true`.||
  ||**<n>** | **object**

  Порядковый номер страницы заданий в массиве при создании (начиная с 0).||
  |#

- Сведения об операции (async_mode=true)

  ```json
  {
    "id": "26e130ad3652443a3dc5094791e48ef9",
    "type": "TASK_SUITE.BATCH.CREATE",
    "status": "FAIL",
    "submitted": "2015-12-13T23:32:01",
    "started": "2015-12-13T23:33:00",
    "finished": "2015-12-13T23:34:12",
    "details": {
      "success_count": 0,
      "failed_count": 2
    }
  }
  ```

  #|
  ||**Параметр** |**Описание**||
  ||**id** | **string**

  Идентификатор операции.||
  ||**type** | **string**

  Тип операции:
  - `POOL.OPEN` — открытие пула;
  - `POOL.CLOSE` — закрытие пула;
  - `PROJECT.ARCHIVE` — отправка проекта в архив;
  - `POOL.ARCHIVE` — отправка пула в архив;
  - `TASK_SUITE.BATCH_CREATE` — создание нескольких страниц заданий.||
  ||**status** | **string**

  Статус операции:
  - `PENDING` — выполнение не началось;
  - `RUNNING` — выполняется;
  - `SUCCESS` — успешно выполнена;
  - `FAIL` — не выполнена.||
  ||**submitted** | **string**

  Дата и время отправки запроса по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
 ||**started** | **string**

 Дата и время начала операции по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
  ||**finished** | **string**

  Дата и время окончания операции по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
  ||**details. success_count** | **integer**

  Количество загруженных страниц заданий.||
  ||**details. failed_count** | **integer**

  Количество страниц заданий, которые не были загружены.||
  |#



{% endlist %}

{% endcut %}
