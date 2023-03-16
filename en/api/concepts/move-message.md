# Move a message thread

{% include [announce](../_includes/announce.md) %}

Adds or removes a message thread from a folder.

Message threads located in the `UNREAD` folder are marked as unread in the interface.

Message threads located in the `IMPORTANT` folder are marked as important in the interface.

## Request {#request}

#### To add to a folder

Adds a message thread to a folder.

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/message-threads/<thread_id>/add-to-folders
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/message-threads/<thread_id>/add-to-folders
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

#### Remove from a folder

Deletes a message thread from a folder.

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/message-threads/<thread_id>/remove-from-folders
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/message-threads/<thread_id>/remove-from-folders
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
  "folders": ["UNREAD", "IMPORTANT"]
}
```

#|
|| Parameter | Overview ||
|| **folders** | **array of strings**

Folders to add a message thread to or remove a message thread from. ||
|#

{% include [contact-support](../../guide/_includes/contact-support.md) %}