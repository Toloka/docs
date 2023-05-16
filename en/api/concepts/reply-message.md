# Reply to message thread

{% include [announce](../_includes/announce.md) %}

Replies to a message thread.

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#post-/message-threads/-id-/reply):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/message-threads/<thread_id>/reply
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/message-threads/<thread_id>/reply
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

{% include [contact-support](../../guide/_includes/contact-support.md) %}