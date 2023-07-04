# Размещение заданий

{% include [announce](../_includes/announce.md) %}

## Перед началом работы {#start}

Выберите платформу, чтобы получить OAuth token:

{% list tabs %}

- Песочница

  1. [Зарегистрируйтесь](../../guide/concepts/access.md) на выбранной платформе, если вы не делали этого ранее.
  1. Получите OAuth-токен в [кабинете заказчика](https://sandbox.toloka.yandex.com/ru/requester/profile/integration).
  1. Во всех примерах используется URL песочницы: `https://sandbox.toloka.dev/api/v1/<путь к ресурсу>`. Если решите переключиться на основную версию, замените URL ресурса на `https://toloka.dev/api/v1/<путь к ресурсу>`.

- Основная версия

  1. [Зарегистрируйтесь](../../guide/concepts/access.md) на выбранной платформе, если вы не делали этого ранее.
  1. Получите OAuth-токен в [кабинете заказчика](https://platform.toloka.ai/ru/requester/profile/integration).
  1. Для отправки запросов замените в примерах URL ресурса на `https://toloka.dev/api/v1/<путь к ресурсу>`, потому что все примеры приведены для песочницы.
  1. Для публикации в основной версии Толоки необходимо предварительно [пополнить баланс счета](../../guide/concepts/refill.md).

{% endlist %}

## Создайте проект {#project}

### Запрос {#project}

Воспользуйтесь методом `POST /api/v1/projects`:

{% list tabs %}

- cURL

    Отправьте запрос из командной строки с помощью утилиты cURL:

    ```bash
    curl -X POST \
         -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
         -H 'Content-Type: application/json' \
         -d '{
               "public_name": "Cat or dog",
               "public_description": "What kind of animal is on the picture?",
               "public_instructions": "Look at the picture. Is it a dog or a cat? Choose the correct answer.",
               "task_spec": {
                 "input_spec": {
                   "image": {
                     "type": "url",
                     "required": true,
                     "hidden": false
                   }
                 },
                 "output_spec": {
                   "result": {
                     "type": "string",
                     "required": true,
                     "hidden": false,
                     "allowed_values": ["cat","dog"]
                   }
                 },
                 "view_spec": {
                   "lock": {
                     "core": "1.7.0",
                     "view.list": "1.0.5",
                     "view.image": "1.2.0",
                     "plugin.toloka": "1.1.8",
                     "field.radio-group": "1.1.10",
                     "condition.required": "1.1.5"
                   },
                   "type": "tb",
                   "config": "{\"view\": {\"items\": [{\"url\": {\"path\": \"image\", \"type\": \"data.input\"}, \"ratio\": [1, 1], \"type\": \"view.image\"}, {\"data\": {\"path\": \"result\", \"type\": \"data.output\"}, \"validation\": {\"type\": \"condition.required\"}, \"options\": [{\"label\": \"Cat\", \"value\": \"cat\"}, {\"label\": \"Dog\", \"value\": \"dog\"}], \"type\": \"field.radio-group\"}], \"type\": \"view.list\"}, \"plugins\": [{\"layout\": {\"kind\": \"scroll\", \"taskWidth\": 400}, \"type\": \"plugin.toloka\"}]}",
                   "settings": {
                     "showSkip": true,
                     "showTimer": true,
                     "showTitle": true,
                     "showFinish": true,
                     "showSubmit": true,
                     "showMessage": true,
                     "showFullscreen": true,
                     "showInstructions": true
                   }
                 }
               },
               "assignments_issuing_type": "AUTOMATED"
             }' \
    https://sandbox.toloka.dev/api/v1/projects
    ```

- Postman

  Заполните поля:

  1. Request URL

    ```bash
    https://sandbox.toloka.dev/api/v1/projects
    ```

  1. Headers

    ```bash
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

  1. Body

        ```json
        {
          "public_name": "Cat or dog",
          "public_description": "What kind of animal is on the picture?",
          "public_instructions": "Look at the picture. Is it a dog or a cat? Choose the correct answer.",
          "task_spec": {
            "input_spec": {
              "image": {
                "type": "url",
                "required": true,
                "hidden": false
              }
            },
            "output_spec": {
              "result": {
                "type": "string",
                "required": true,
                "hidden": false,
                "allowed_values": [
                  "cat",
                  "dog"
                ]
              }
            },
            "view_spec": {
              "lock": {
                "core": "1.7.0",
                "view.list": "1.0.5",
                "view.image": "1.2.0",
                "plugin.toloka": "1.1.8",
                "field.radio-group": "1.1.10",
                "condition.required": "1.1.5"
              },
              "type": "tb",
              "config": "{\"view\": {\"items\": [{\"url\": {\"path\": \"image\", \"type\": \"data.input\"}, \"ratio\": [1, 1], \"type\": \"view.image\"}, {\"data\": {\"path\": \"result\", \"type\": \"data.output\"}, \"validation\": {\"type\": \"condition.required\"}, \"options\": [{\"label\": \"Cat\", \"value\": \"cat\"}, {\"label\": \"Dog\", \"value\": \"dog\"}], \"type\": \"field.radio-group\"}], \"type\": \"view.list\"}, \"plugins\": [{\"layout\": {\"kind\": \"scroll\", \"taskWidth\": 400}, \"type\": \"plugin.toloka\"}]}",
              "settings": {
                "showSkip": true,
                "showTimer": true,
                "showTitle": true,
                "showFinish": true,
                "showSubmit": true,
                "showMessage": true,
                "showFullscreen": true,
                "showInstructions": true
              }
            }
          },
          "assignments_issuing_type": "AUTOMATED"
        }
        ```

{% endlist %}

В примере приведены основные параметры, которые необходимы для создания простейшего проекта. Более подробное описание всех параметров запроса приведено в разделе [Создать проект](create-prj.md).

### Ответ {#project}

В ответе на запрос вы получите JSON-объект созданного проекта. Объект будет содержать идентификатор проекта (`id`).

```json
{
  "id": "12345",
  "public_name": "Cat or dog",
  "public_description": "What kind of animal is on the picture?",
  ...
}
```

{% note warning %}

`id` потребуется для создания пулов в проекте — укажите его в запросе на добавление пула.

{% endnote %}

## Добавьте пул {#pool}

### Запрос {#pool-post}

В приведенном примере кода подставьте значения параметров:

- в `project_id` вместо `<project id>` — идентификатор проекта, для которого создан пул (id, полученный в ответ на запрос на добавление проекта);
- в `will_expire` вместо `<close date>` — дату и время по UTC в формате `ISO 8601: YYYY-MM-DDThh:mm:ss[.sss]`, когда пул нужно закрыть, даже если не все страницы заданий выполнены.

Затем отправьте POST-запрос к `/api/v1/pools`:

{% list tabs %}

- cURL

    {% include [project-bash](../_includes/concepts/qs-placement/id-project/bash.md) %}

    ```bash
    curl -X POST \
         -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
         -H 'Content-Type: application/json' \
         -d '{
               "project_id": "<project id>",
               "private_name": "Cat pool 1",
               "may_contain_adult_content": true,
               "will_expire": "<close date>",
               "reward_per_assignment": 0.02,
               "assignment_max_duration_seconds": 60,
               "filter": {
                 "and": [
                   {
                     "or": [
                       {
                         "category": "profile",
                         "key": "languages",
                         "operator": "IN",
                         "value": "RU"
                       }
                     ]
                   }
                 ]
               },
               "quality_control": {
                 "captcha_frequency": "LOW",
                 "configs": [
                   {
                     "collector_config": {
                       "type": "CAPTCHA",
                       "parameters": {
                         "history_size": 10
                       }
                     },
                     "rules": [
                       {
                         "conditions": [
                           {
                             "key": "stored_results_count",
                             "operator": "EQ",
                             "value": 10
                           },
                           {
                             "key": "success_rate",
                             "operator": "LTE",
                             "value": 70.0
                           }
                         ],
                         "action": {
                           "type": "RESTRICTION_V2",
                           "parameters": {
                             "scope": "PROJECT",
                             "duration_unit": "DAYS",
                             "duration": 3,
                             "private_comment": "Incorrect captcha input"
                           }
                         }
                       }
                     ]
                   }
                 ]
               },
               "mixer_config": {
                 "real_tasks_count": 3,
                 "golden_tasks_count": 0,
                 "training_tasks_count": 0
               },
               "defaults": {
                 "default_overlap_for_new_task_suites": 3
               }
             }' \
    https://sandbox.toloka.dev/api/v1/pools
    ```

- Postman

    {% include [project-postman-fields](../_includes/concepts/qs-placement/id-project/postman-fields.md) %}

  1. Request URL

    ```bash
    https://sandbox.toloka.dev/api/v1/pools
    ```

  1. Headers

    ```bash
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

  1. Body

        ```json
        {
          "project_id": "<project id>",
          "private_name": "Cat pool 1",
          "may_contain_adult_content": true,
          "will_expire": "<close date>",
          "reward_per_assignment": 0.02,
          "assignment_max_duration_seconds": 60,
          "filter": {
            "and": [
              {
                "or": [
                  {
                    "category": "profile",
                    "key": "languages",
                    "operator": "IN",
                    "value": "RU"
                  }
                ]
              }
            ]
          },
          "quality_control": {
            "captcha_frequency": "LOW",
            "configs": [
              {
                "collector_config": {
                  "type": "CAPTCHA",
                  "parameters": {
                    "history_size": 10
                  }
                },
                "rules": [
                  {
                    "conditions": [
                      {
                        "key": "stored_results_count",
                        "operator": "EQ",
                        "value": 10
                      },
                      {
                        "key": "success_rate",
                        "operator": "LTE",
                        "value": 70
                      }
                    ],
                    "action": {
                      "type": "RESTRICTION_V2",
                      "parameters": {
                        "scope": "PROJECT",
                        "duration_unit": "DAYS",
                        "duration": 3,
                        "private_comment": "Incorrect captcha input"
                      }
                    }
                  }
                ]
              }
            ]
          },
          "mixer_config": {
            "real_tasks_count": 3,
            "golden_tasks_count": 0,
            "training_tasks_count": 0
          },
          "defaults": {
            "default_overlap_for_new_task_suites": 3
          }
        }
        ```

{% endlist %}

В примере приведены основные параметры, которые необходимы для создания простейшего пула. Более подробное описание всех параметров запроса содержится в разделе [Создать пул](create-pool.md).

### Ответ {#pool}

В ответе на запрос вы получите JSON-объект созданного пула. Объект будет содержать идентификатор пула (`id`).

```json
{
  "id": "9876543",
  "project_id": "12345",
    "private_name": "Cat pool 1",
    ...
}
```

{% note warning %}

`id` потребуется для добавления заданий в пул — укажите его в запросе на загрузку заданий.

{% endnote %}

## Загрузите задания {#task}

### Запрос {#tasks-post}

В приведенном примере кода подставьте значения параметров:

- в `input_values` вместо `<proxy name>`/`<folder name>`/`<file name N>.<type>` — конкретные значения для входных данных, которые были опеределены в параметре `input_spec` проекта (в данном примере — адреса изображений для разметки, сами файлы в этом случае необходимо разместить на Яндекс Диске и добавить его как [прокси](../../guide/concepts/prepare-data.md) в качестве источника данных);
- в `pool_id` вместо `<pool id>` — идентификатор пула, в который загружается задание (id, полученный в ответ на запрос на добавление пула).

Затем отправьте POST-запрос к `/api/v1/tasks`:

{% list tabs %}

- cURL

  {% include [project-bash](../_includes/concepts/qs-placement/id-project/bash.md) %}

    ```bash
    curl -X POST \
         -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
         -H 'Content-Type: application/json' \
         -d '[
               {
                 "input_values": {
                   "image": "https://sandbox.toloka.dev/api/proxy/<proxy name>/<folder name>/<file name 1>.<type>"
                 },
                 "pool_id": "<pool id>",
                 "overlap": 2
               },
               {
                 "input_values": {
                   "image": "https://sandbox.toloka.dev/api/proxy/<proxy name>/<folder name>/<file name 2>.<type>"
                 },
                 "pool_id": "<pool id>",
                 "overlap": 2
               },
               {
                 "input_values": {
                   "image": "https://sandbox.toloka.dev/api/proxy/<proxy name>/<folder name>/<file name 3>.<type>"
                 },
                 "pool_id": "<pool id>",
                 "overlap": 2
               }
             ]' \
    https://sandbox.toloka.dev/api/v1/tasks
    ```

- Postman

  {% include [project-postman-fields](../_includes/concepts/qs-placement/id-project/postman-fields.md) %}

  1. Request URL

    ```bash
    https://sandbox.toloka.dev/api/v1/tasks
    ```

  1. Headers

    ```bash
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

  1. Body

        ```json
        [
          {
            "input_values": {
              "image": "https://sandbox.toloka.dev/api/proxy/<proxy name>/<folder name>/<file name 1>.<type>"
            },
            "pool_id": "<pool id>",
            "overlap": 2
          },
          {
            "input_values": {
              "image": "https://sandbox.toloka.dev/api/proxy/<proxy name>/<folder name>/<file name 2>.<type>"
            },
            "pool_id": "<pool id>",
            "overlap": 2
          },
          {
            "input_values": {
              "image": "https://sandbox.toloka.dev/api/proxy/<proxy name>/<folder name>/<file name 3>.<type>"
            },
            "pool_id": "<pool id>",
            "overlap": 2
          }
        ]
        ```

{% endlist %}

В примере приведены основные параметры, которые необходимы для загрузки простейших заданий. Более подробное описание всех параметров заданий приведено в разделе [Создать одно или несколько заданий](create-task.md).

## Запустите пул {#pool-run}

### Перед запуском {#pool-run}

Перед запуском пула перейдите в интерфейс Толоки, выберите пул, нажмите кнопку **Предпросмотр** и проверьте отображение заданий.

### Запрос {#pool-run}

В path-параметр `<pool_id>` подставьте id пула, который нужно запустить (id, полученный в ответе на запрос на добавление пула), и воспользуйтесь методом `POST`:

{% list tabs %}

- cURL

  {% include [project-bash](../_includes/concepts/qs-placement/id-project/bash.md) %}

    ```bash
    curl -X POST \
      -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
      -H 'Content-Type: application/json' \
    https://sandbox.toloka.dev/api/v1/pools/<pool_id>/open
    ```

- Postman

  {% include [project-postman-fields](../_includes/concepts/qs-placement/id-project/postman-fields.md) %}

  1. Request URL

        ```bash
        https://sandbox.toloka.dev/api/v1/pools/<pool_id>/open
        ```

  1. Headers

        ```bash
        Authorization: OAuth PlaceYourRealOAuthToken_Here
        Content-Type: application/json
        ```

{% endlist %}

## Проверьте задания {#check}

После запуска пула убедитесь, что все настройки и отображение заданий
 корректны. Для этого [зайдите в Толоку под логином исполнителя]({{ toloka-web-register }}) и откройте карточку с созданными заданиями.

## Что дальше {#what-next}

Почитайте [инструкцию по получению результатов](qs-results.md).

## Узнайте больше {#links-qs-placement}

- [HTTP-методы для работы с проектами](project.md)
- [HTTP-методы для работы с пулами](pool.md)
- [HTTP-методы для загрузки заданий](tasks.md)