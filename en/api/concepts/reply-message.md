# Reply to message thread

Replies to a message thread.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.yandex.com/api/v1/message-threads/<thread_id>/reply
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.yandex.com/api/v1/message-threads/<thread_id>/reply
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**thread_id** | Message thread ID.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

```json
{
  "text": {
    "EN": "Thank you!"
  }
}
```

#|
|| Parameter | Overview ||
|| **text** | **string**

Message text. You can enter the text in multiple languages (the message is sent in the Toloker's language). Format: `"<language RU/EN/TR/ID/FR>": "<message text>"`. ||
|#