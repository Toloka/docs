# Close a pool for editing

{% include [announce](../_includes/announce.md) %}

Closes a pool for editing.

To make changes to a pool, close it before editing.

{% note info %}

If you don't open the pool manually after editing, it opens automatically in 15 minutes. In this case, no checks are performed that can block the pool's opening.

{% endnote %}

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/pools/<pool_id>/close-for-update
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/pools/<pool_id>/close-for-update
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**pool_id** | Pool ID.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Response {#response}

{% note info %}

If the current pool status is the same as the  requested status, an empty response with status 204 is returned.

{% endnote %}

```json
{
  "id": "019587fd-b536-49f8-b6dc-01ffc25f8594",
  "type": "POOL.CLOSE",
  "status": "PENDING",
  "submitted": "2021-11-24T07:47:50.120",
  "started" : "2021-11-24T07:47:50.120",
  "finished" : "2021-11-24T07:47:50.120",
  "progress" : 100,
  "parameters": {
    "pool_id": "21"
  }
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**

User ID. ||
|| **type** | **string**

Type of operation: `POOL.CLOSE` — Closing a pool. ||
|| **status** | **string**

The status of the operation:

- `PENDING` — Not started yet.
- `RUNNING` — In progress.
- `SUCCESS` — Completed successfully.
- `FAIL` — Not completed. ||
|| **submitted** | **string**

The UTC date and time the request was sent, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **started** | **string**

The UTC date and time the operation started, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **finished** | **string**
The UTC date and time the operation was completed, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **progress** | **integer**
The percentage of the operation completed. ||
|| **parameters.pool_id** | **string**
Pool ID. ||
|#