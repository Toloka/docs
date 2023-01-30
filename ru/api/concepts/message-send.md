# Отправить сообщение

{% include [announce](../_includes/announce.md) %}

Рассылает сообщение исполнителям.

- [Указать адресатов списком](#spis).
- [Отобрать исполнителей с помощью фильтра](#didi).

Отправленное сообщение добавляется в новую [цепочку сообщений](messages.md).

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    POST https://toloka.dev/api/v1/message-threads/compose
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Песочница

    ```bash
    POST https://sandbox.toloka.dev/api/v1/message-threads/compose
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

#### Сообщение со списком адресатов

```json
{
  "topic": {
    "EN": "You have got a bonus!"
  },
  "text": {
    "EN": "The bonus was awarded for good job!"
  },
  "recipients_select_type": "DIRECT",
  "recipients_ids": [
    "2225cfb24c15b7d691818f5ac9d07f70"
  ],
  "answerable": true
}
```

#|
||**Параметр**| **Описание**||
||**topic** | **object \| обязательный**

Заголовок сообщения. Можно привести заголовок на нескольких языках (сообщение придет на языке исполнителя). Формат:

 `"<язык RU/EN/TR/ID/FR>": "<текст заголовка>"`.||
||**answerable** | **boolean \| обязательный**

Возможность ответить на сообщение:

- `true` — исполнитель может ответить на сообщение.
- `false` — исполнитель не может ответить на сообщение.

По умолчанию значение `true.`||
||**text** | **object \| обязательный**

Текст сообщения. Можно привести текст на нескольких языках (сообщение придет на языке исполнителя). Формат:

 `"<язык RU/EN/TR/ID/FR>": "<текст сообщения>"`.||
||**recipients_select_type** | **string \| обязательный**

Способ указания адресатов:

- `DIRECT` — указать идентификаторы
 исполнителей.
 - `FILTER` — отобрать исполнителей с помощью [фильтра](filters.md).
 - `ALL` — отправить сообщение всем исполнителям, которые хотя бы раз пытались выполнять ваши задания.||
||**recipients_ids** | **object \| обязательный при условии**

Обязателен, если `recipients_select_typ`. Список идентификаторов исполнителей, которым будет отправлено сообщение.||
|#

#### Сообщение с фильтром

```json
{
  "topic": {
    "EN": "You have got a bonus!"
  },
  "text": {
    "EN": "The bonus was awarded for good job!"
  },
  "recipients_select_type": "FILTER",
  "recipients_filter": {
    "and": [
      {
        "category": "skill",
        "key": "2022",
        "operator": "GT",
        "value": 90
      }
    ]
  },
  "answerable": true
}
```

#|
||**Параметр**| **Описание**||
||**topic** | **object \| обязательный**

Заголовок сообщения. Можно привести заголовок на нескольких языках (сообщение придет на языке исполнителя). Формат:

 `"<язык RU/EN/TR/ID/FR>": "<текст заголовка>"`.||
||**answerable** | **boolean \| обязательный**

Возможность ответить на сообщение:

- `true` — исполнитель может ответить на сообщение.
- `false` — исполнитель не может ответить на сообщение.

По умолчанию значение `true.`||
||**text** | **object \| обязательный**

Текст сообщения. Можно привести текст на нескольких языках (сообщение придет на языке исполнителя). Формат:

 `"<язык RU/EN/TR/ID/FR>": "<текст сообщения>"`.||
||**recipients_select_type** | **string \| обязательный**

Способ указания адресатов:

- `DIRECT` — указать идентификаторы
 исполнителей.
 - `FILTER` — отобрать исполнителей с помощью [фильтра](filters.md).
 - `ALL` — отправить сообщение всем исполнителям, которые хотя бы раз пытались выполнять ваши задания.||
||**recipients_filter** | **object \| обязательный при условии**

Обязателен, если `recipients_select_type=FILTER`.

[Фильтр](filters.md) для отбора адресатов||
|#

## Ответ {#response}

В ответ вы получите сообщение в виде новой цепочки.

```json
{
  "id": "558110f401d292324c0da8bd",
  "topic": {
    "EN": "You received a reward!"
  },
  "interlocutors_inlined": true,
  "interlocutors": [
    {
      "id": "111bd25f1bb71f37844e2a9355faad67",
      "role": "REQUESTER",
      "myself": true
    },
    {
      "id": "2225cfb24c15b7d691818f5ac9d07f70",
      "role": "USER"
    }
  ],
  "messages_inlined": true,
  "messages": [
    {
      "text": {
        "EN": "Thank you!"
      },
      "from": {
        "id": "2225cfb24c15b7d691818f5ac9d07f70",
        "role": "USER"
        },
        "created": "2017-01-31T11:02:31"
    {
      "text": {
        "EN": "You received a reward for doing a good job!"
      },
      "from": {
        "id": "111bd25f1bb71f37844e2a9355faad67",
        "role": "REQUESTER",
        "myself": true
      },
      "created": "2017-01-31T09:38:01"
    }
  ],
  "compose_details": {
    "recipients_select_type": "DIRECT",
    "recipients_ids": [
      "2225cfb24c15b7d691818f5ac9d07f70"
    ]
  },
  "answerable": true,
  "folders": [
    "INBOX",
    "OUTBOX"
  ],
  "created": "2017-01-31T09:38:01"
}
```

#|
||**Параметр**| **Описание**||
||**id** | **string**

Идентификатор цепочки сообщений.||
||**topic** | **object**

Заголовок цепочки сообщений.||
||**interlocutors_inlined** | **boolean**

Доступ к сведениям об отправителе и адресатах.

- `true` — сведения доступны в поле `interlocutors`.
- `false` — сведения доступны по отдельному запросу.||
||**interlocutors[]** | **array of objects**

Сведения об отправителе и адресатах, отсортированные по идентификаторам.||
||**interlocutors.id** | **string**

Идентификатор отправителя или адресата.||
||**interlocutors.role** | **string**

Роль отправителя или адресата в Толоке:

- `USER` — исполнитель.
- `REQUESTER` — заказчик.
- `ADMINISTRATOR` — администратор.
- `SYSTEM` — для сообщений, отправленных автоматически.||
||**interlocutors.myself** | **boolean**

Маркер отправителя или адресата с вашим идентификатором. Если идентификатор принадлежит вам, указывается значение `true`.||
||**messages_inlined** | **boolean**

Доступ к сообщениям цепочки:

- `true` — сообщение доступно в поле `messages`.
- `false` — сообщение доступно по отдельному запросу.||
||**messages[]** | **array of objects**

Сообщения в цепочке. Отсортированы по дате создания (сначала новые).||
||**messages.text** | **object**

Текст сообщения.||
||**messages.from** | **string**

Сведения об отправителе сообщения.||
||**messages.from.id** | **string**

Идентификатор отправителя.||
||**messages.from.role** | **string**

Роль отправителя в Толоке:

- `USER` — исполнитель.
- `REQUESTER` — заказчик.
- `ADMINISTRATOR` — администратор.
- `SYSTEM` — сообщение было отправлено автоматически.||
||**messages.from.myself** | **boolean**

Маркер отправителя с вашим идентификатором. Если отправитель — это вы, указывается значение `true`.||
||**messages.created** | **string**

Дата создания сообщения.||
||**compose_details** | **object**

Для сообщений, отправленных вами: детали POST-запроса для создания сообщения.||
||**compose_details.recipients_select_type** | **string**

Способ указания адресатов:

- `DIRECT` — указать идентификаторы исполнителей.
- `FILTER` — отобрать исполнителей с помощью [фильтра](filters.md).
- `ALL` — отправить сообщение всем исполнителям, которые хотя бы раз пытались выполнять ваши задания.||
||**compose_details.recipients_ids** | **object**

Список идентификаторов исполнителей, которым будет отправлено сообщение.||
||**compose_details.recipients_filter** | **object**

[Фильтр](filters.md) для отбора адресатов.||
||**answerable** | **boolean**

Возможность ответить на сообщение:

- `true` — исполнитель может ответить на сообщение.
- `false` — исполнитель не может ответить на сообщение.||
||**folders[]** | **array of objects**

Папки, в которых находится цепочка:

- `INBOX` — Входящие.
- `OUTBOX` — Отправленные.
- `AUTOMATIC_NOTIFICATION` — Уведомления.
- `IMPORTANT` — Важные.
- `UNREAD` — Непрочитанные.||
||**created** | **string**

Дата создания первого сообщения в цепочке.||
|#