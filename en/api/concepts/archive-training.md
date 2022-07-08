# Archive a training pool

Moves a training pool to the archive.

If a training pool isn't in use, it can be moved to the archive. Before archiving, check two conditions:

- The training pool must have the "closed" status.
- All the main pools that the training pool is linked to must be [sent to the archive](archive-pool.md).

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.yandex.com/api/v1/training/<training_id>/archive
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.yandex.com/api/v1/training/<training_id>/archive
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**training_id** | Pool ID.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Response {#response}

{% note info %}

If the training pool is already archived, attempting to archive it again returns an empty response with status 204.

{% endnote %}

```json
{
  "id": "95029e60-eace-4a3e-96b9-c72c5e727218",
  "type": "TRAINING.ARCHIVE",
  "status": "SUCCESS",
  "submitted": "2021-02-26T10:13:32.921",
  "started": "2021-02-26T10:13:32.921",
  "finished": "2021-02-26T10:13:32.921",
  "progress": 100,
  "parameters": {
    "training_id": "123456"
  },
  "details": {}
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**

User ID. ||
|| **type** | **string**
Type of operation: `TRAINING.ARCHIVE` — Archive a training pool. ||
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
|| **parameters.training_id** | **string**
ID of the training pool. ||
|| **details** | **object**
Details of the operation completion. ||
|#