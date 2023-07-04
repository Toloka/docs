# Получение результатов

{% include [announce](../_includes/announce.md) %}

Приведенный пример создавался в песочнице, поэтому для дальнейшей обработки результатов необходимо выполнить задания от лица доверенного пользователя:

1. Зарегистрируйтесь в [песочнице Толоки]({{ sandbox }}) в качестве заказчика.

1. Зайдите в песочницу с логином заказчика и перейдите по ссылке  на странице [Пользователи]({{ sandbox-workers }}).

1. Нажмите кнопку  и введите логин созданного аккаунта.

1. Выполните задания в песочнице с логином доверенного пользователя.

Если выполнено хотя бы одно задание из пула, вы можете получить ответы.

В приведенном примере от исполнителей не требовалось загружать какие-либо файлы в ответ к заданиям. Поэтому можно получить сами ответы исполнителей.

## Получите ответы {#get-responses}

### Запрос {#get-responses}

В query-параметре `pool_id` вместо `<pool id>` подставьте id пула, для которого надо получить ответы (id, полученный в ответе на [запрос на добавление пула](qs-placement.md)).

Затем воспользуйтесь методом `GET`:

{% list tabs %}

- cURL

  {% include [project-bash](../_includes/concepts/qs-placement/id-project/bash.md) %}

  ```bash
  curl -X GET \
       -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
  https://sandbox.toloka.dev/api/v1/assignments?pool_id=<pool id>
  ```

- Postman

  {% include [project-postman-fields](../_includes/concepts/qs-placement/id-project/postman-fields.md) %}

  1. Request URL

      ```bash
      https://sandbox.toloka.dev/api/v1/assignments?pool_id=<pool id>
      ```

  1. Headers

      ```bash
      Authorization: OAuth PlaceYourRealOAuthToken_Here
      ```

{% endlist %}

### Ответ {#get-responses}

Ответы исполнителей возвращаются в массиве `items` в формате:

```json
{
  "items": [
    {
      "id": "00000f80eb-–617d0d2f515c446d68cc2785",
      "task_suite_id": "00000f80eb-–617d0d2f515c446d68cc2783",
      "pool_id": "9876543",
      "user_id": "f2a33d6eb1d3c8f9c917adbf259c0539",
      "status": "ACCEPTED",
      "reward": 0.02,
      "tasks": [
        {
          "id": "00000f80eb--617d0cbba52cc70d7118c5bc",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/3.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:31.153",
          "remaining_overlap": 0
        },
        {
          "id": "00000f80eb--617d0cbaa52cc70d7118c5b8",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/1.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:30.951",
          "remaining_overlap": 0
        },
        {
          "id": "00000f80eb--617d0cbba52cc70d7118c5ba",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/2.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:31.069",
          "remaining_overlap": 0
        }
      ],
      "solutions": [
        {
          "output_values": {
            "result": "dog"
          }
        },
        {
          "output_values": {
            "result": "cat"
          }
        },
        {
          "output_values": {
            "result": "dog"
          }
        }
      ],
      "mixed": true,
      "automerged": false,
      "created": "2021-10-30T09:15:27.217",
      "submitted": "2021-10-30T09:15:36.570",
      "accepted": "2021-10-30T09:15:36.570",
      "owner": {
        "id": "9ea475935832de1dde0ece716c9df178",
        "myself": true
      }
    },
    {
      "id": "00000f80eb--617d0d82a52cc70d7118c614",
      "task_suite_id": "00000f80eb--617d0d82a52cc70d7118c612",
      "pool_id": "1016043",
      "user_id": "d01e518a746b149b07b81a10f4cfb1c2",
      "status": "ACCEPTED",
      "reward": 0.02,
      "tasks": [
        {
          "id": "00000f80eb--617d0cbba52cc70d7118c5ba",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/2.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:31.069",
          "remaining_overlap": 0
        },
        {
          "id": "00000f80eb--617d0cbba52cc70d7118c5bc",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/3.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:31.153",
          "remaining_overlap": 0
        },
        {
          "id": "00000f80eb--617d0cbaa52cc70d7118c5b8",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/1.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:30.951",
          "remaining_overlap": 0
        }
      ],
      "solutions": [
        {
          "output_values": {
            "result": "cat"
          }
        },
        {
          "output_values": {
            "result": "dog"
          }
        },
        {
          "output_values": {
            "result": "cat"
          }
        }
      ],
      "mixed": true,
      "automerged": false,
      "created": "2021-10-30T09:16:50.542",
      "submitted": "2021-10-30T09:16:59.739",
      "accepted": "2021-10-30T09:16:59.739",
      "owner": {
        "id": "9ea475935832de1dde0ece716c9df178",
        "myself": true
      }
    }
  ],
  "has_more": false
}
```

Нажмите на параметр в примере ответа, чтобы увидеть его краткое описание.

## Узнайте больше {#links-qs-results}

- [HTTP-методы для обработки ответов исполнителей](get-response.md)
- [HTTP-методы для обработки файлов в ответах исполнителей](attachments.md)
- [Агрегация ответов](aggregated-solutions.md)
- [Использование библиотек](libraries.md)