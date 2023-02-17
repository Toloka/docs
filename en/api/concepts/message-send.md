# To send a message

{% include [announce](../_includes/announce.md) %}

Sends a message to Tolokers.

- [Specify recipients in a list](#spis).
- [Select Tolokers using a filter](#didi).

The sent message is added to a new [message thread](messages.md).

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/message-threads/compose
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/message-threads/compose
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

{% list tabs %}

- Message with a list of recipients {#spis}

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
  || Parameter  | Overview ||
  || **topic** | **object \| required**

    Subject of the message. You can enter the subject in multiple languages (the message is sent in the Toloker's language). Format: `"<language RU/EN/TR/ID/FR>": "<title text>"`. ||
  || **answerable** | **boolean \| required**

    Whether the message can be responded to:

    - `true` — Users can respond to the message.
    - `false` — Users can't respond to the  message.

    The default value is `true`. ||
  || **text** | **object \| required**

    Message text. You can enter the text in multiple languages (the message is sent in the Toloker's language). Format: `"<language RU/EN/TR/ID/FR>": "<message text>"`. ||
  || **recipients_select_type** | **string \| required**

    Method for selecting recipients:

    - `DIRECT` — Specify Toloker IDs.
    - `FILTER` — Use a [filter](filters.md) to select Tolokers.
    - `ALL` — Send the message to all Tolokers who have tried to complete your tasks at least once. ||
  || **recipients_ids** | **object \| required if**

    Required if `recipients_select_typ`. The list of IDs of Tolokers who will receive the message. ||
  |#

- Filter message {#didi}

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
  || Parameter  | Overview ||
  || **topic** | **object \| required**

    Subject of the message. You can enter the subject in multiple languages (the message is sent in the Toloker's language). Format: `"<language RU/EN/TR/ID/FR>": "<title text>"`. ||
  || **answerable** | **boolean \| required**

    Whether the message can be responded to:

    - `true` — Users can respond to the message.
    - `false` — Users can't respond to the  message.

    The default value is `true`. ||
  || **text** | **object \| required**

    Message text. You can enter the text in multiple languages (the message is sent in the Toloker's language). Format: `"<language RU/EN/TR/ID/FR>": "<message text>"`. ||
  || **recipients_select_type** | **string \| required**

    Method for selecting recipients:

    - `DIRECT` — Specify Toloker IDs.
    - `FILTER` — Use a [filter](filters.md) to select Tolokers.
    - `ALL` — Send the message to all Tolokers who have tried to complete your tasks at least once. ||
  || **recipients_filter** | **object \| required if**

    Required if `recipients_select_type=FILTER`.

    [Filter](filters.md) for selecting recipients. ||
  |#

{% endlist %}

## Response {#response}

In response, you will receive a message as a new thread.

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
|| Parameter | Overview ||
|| **id** | **string**

Message thread ID. ||
|| **topic** | **object**

Message thread title. ||
|| **interlocutors_inlined** | **boolean**

Access to information about the sender and recipients.

- `true` — Information is available in the `interlocutors` field.
- `false` — Information is available in a separate request. ||
|| **interlocutors[]** | **array of objects**

Information about the sender and recipients, sorted by ID. ||
|| **interlocutors.id** | **string**

ID of the sender or recipient. ||
|| **interlocutors.role** | **string**

Role of the sender or recipient in Toloka:

- `USER` — Toloker.
- `REQUESTER` — Requester.
- `ADMINISTRATOR` — Admin.
- `SYSTEM` — For messages sent automatically. ||
|| **interlocutors.myself** | **boolean**

Indicates a sender or recipient with your ID. If this is your ID, it is set to `true`. ||
|| **messages_inlined** | **boolean**

Access to message threads:

- `true` — The message is available in the `messages` field.
- `false` — The message is available in a separate request. ||
|| **messages[]** | **array of objects**

Messages in the thread. Messages are sorted by date of creation (newest first). ||
|| **messages.text** | **object**

Message text. ||
|| **messages.from** | **string**

Information about the sender. ||
|| **messages.from.id** | **string**

The sender's ID. ||
|| **messages.from.role** | **string**

The sender's role in Toloka:

- `USER` — Toloker.
- `REQUESTER` — Requester.
- `ADMINISTRATOR` — Admin.
- `SYSTEM` — For messages sent automatically. ||
|| **messages.from.myself** | **boolean**

Marks a sender with your ID. If you are the sender, it is set to `true`. ||
|| **messages.created** | **string**

Date the message was created. ||
|| **compose_details** | **object**

For messages that you sent: details of the POST request for creating the message. ||
|| **compose_details.recipients_select_type** | **string**

Method for selecting recipients:

- `DIRECT` — Specify Toloker IDs.
- `FILTER` — Use a [filter](filters.md) to select Tolokers.
- `ALL` — Send the message to all Tolokers who have tried to complete a task at least once. ||
|| **compose_details.recipients_ids** | **object**

The list of IDs of Tolokers who will receive the message. ||
|| **compose_details.recipients_filter** | **object**

[Filter](filters.md) for selecting recipients. ||
|| **answerable** | **boolean**

Whether the message can be responded to:

- `true` — The Toloker can respond to the message.
- `false` — The Toloker cannot respond to the message. ||
|| **folders**[] | **array of objects**

Folders where the thread is located:
- `INBOX` — Inbox.
- `OUTBOX` — Sent.
- `AUTOMATIC_NOTIFICATION` — Notifications.
- `IMPORTANT` — Important.
- `UNREAD` — Unread. ||
|| **created** | **string**

Date the first message in the thread was created. ||
|#

{% include [contact-support](../../guide/_includes/contact-support.md) %}