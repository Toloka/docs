# Get a list of message threads

Gets the list of message threads.

## Request {#request}

{% list tabs %}

- Production version

    ```json
    GET https://toloka.yandex.com/api/v1/message-threads
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```json
    GET https://sandbox.toloka.yandex.com/api/v1/message-threads
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | ----- 
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **folder** | **string**

Folders where the thread is located:
- `INBOX` — Inbox.
- `OUTBOX` — Sent.
- `AUTOMATIC_NOTIFICATION` — Notifications.
- `IMPORTANT` — Important.
- `UNREAD` — Unread. ||
|| **folder_ne** | **string**
Folders to not search for the thread: You can specify multiple comma-separated values. ||
|| **sort** | **string**

Parameters to sort by:

- `id` — The ID of a task suite.
    
- `created` — The task suite creation date in UTC using ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss].
    

To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **Standard query parameters** | 
[limit](./standard-query-parameters.md#limit), [id_gt](./standard-query-parameters.md#id_gt), [id_gte](./standard-query-parameters.md#id_gte), [id_lt](./standard-query-parameters.md#id_lt), [id_lte](./standard-query-parameters.md#id_lte), [created_gt](./standard-query-parameters.md#created_gt), [created_gte](./standard-query-parameters.md#created_gte), [created_lt](./standard-query-parameters.md#created_lt), [created_lte](./standard-query-parameters.md#created_lte). ||
|#
