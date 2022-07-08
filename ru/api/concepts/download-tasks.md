# Способы загрузки заданий

## Загрузка заданий с помощью API {#download-tasks-api}

В Толоке с помощью API задания можно загрузить двумя способами:

#### Загрузить каждое задание по отдельности

Выбирайте этот способ, если:

- при [создании пула](create-pool.md) вы применили «умное смешивание» (параметр `mixer_config`);

- в пуле кроме основных будут контрольные или обучающие задания.

При этом способе Толока разобьет задания на страницы в соответствии с настройками «умного смешивания». При загрузке заданий этим способом используйте запрос [POST /tasks](create-task.md).

Подробнее про «умное смешивание» читайте в [Руководстве заказчика]({{ requester-mixing }}).

{% cut "Пример запроса" %}

```bash
POST https://toloka.yandex.com/api/v1/tasks
Authorization: OAuth <OAuth token>
Content-Type: application/JSON

// одно задание
{task data}

// несколько заданий
[{task 1}, {task 2},... {task n}]
```

Тело запроса:

```json
{
   "pool_id": "1",
   "input_values": {
      "image_url": "www.images/image1.ru"
   },
   "known_solutions": [
      {
         "output_values": {
            "result": "OK",
            "like": false
         },
         "correctness_weight": 0.8
      },
      {
         "output_values": {
            "result": "OK",
            "like": true
         },
         "correctness_weight": 1
      },
    ],
   "baseline_solutions": [
      {
         "output_values": {
            "result": "OK",
            "like": false
         },
         "confidence_weight": 0.8
      },
      {
         "output_values": {
            "result": "OK",
            "like": true
         },
         "confidence_weight": 1
      }
   ],
   "message_on_unknown_solution": "The cat is in a good mood.",
   "overlap": 3,
   "infinite_overlap": false,
   "reserved_for": [],
   "unavailable_for": []
}
```

{% endcut %}

#### Загрузить задания, сгруппированные по страницам

Выбирайте этот способ, если вы:

- самостоятельно формируете страницы заданий;

- сами определяете, какие именно задания будут находиться на каждой странице.


Этот способ не подойдет, если при создании пула вы применили [«умное смешивание»]({{ requester-mixing }}). При загрузке заданий этим способом используйте запрос [POST /task-suites](create-task-suite.md).

{% cut "Пример запроса" %}

```bash
POST https://toloka.yandex.com/api/v1/task-suites
Authorization: OAuth <OAuth token>
Content-Type: application/JSON

// одна страница заданий
{task suite parameters}

// несколько страниц заданий
[{task suite 1}, {task suite 2},... {task suite N}]
```

Тело запроса:

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

{% endcut %}

## Загрузка заданий с помощью Python SDK {#download-tasks-python}

Если вы разрабатываете приложения на Python, то можете создавать запросы к API с помощью методов [Toloka Kit]({{ toloka-kit-doc }}), чтобы получить результат с меньшими трудозатратами и избежать возможных ошибок.

Способы загрузки заданий с помощью Toloka Kit:

Способ | Метод
----- | -----
Создает новое задание. | [create_task]({{ tk-create-task }})
Создает несколько заданий в рамках одного запроса. | [create_tasks]({{ tk-create-tasks }})
Создает несколько заданий асинхронно. | [create_tasks_async]({{ tk-create-tasks-async }})
Создает страницу заданий. | [сreate_tasks_suite]({{ tk-create-tasks-suite }})
Создает несколько страниц заданий в рамках одного запроса. | [create_tasks_suites]({{ tk-create-tasks-suites }})
Создает несколько страниц заданий асинхронно. | [create_tasks_suites_async]({{ tk-create-tasks-suites-async }})
