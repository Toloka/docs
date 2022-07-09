# Close a training

Closes a training pool.

To stop assigning training tasks to Tolokers, close the training pool.

When you send requests, an operation is created. To track the progress of the operation, send a request to the `/operations` resource.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.yandex.com/api/v1/trainings/<training_id>/close
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.yandex.com/api/v1/trainings/<training_id>/close
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

If the current training pool status is the same as the requested status, an empty response with status 204 is returned.

{% endnote %}

```json
{
  "id": "52829015-033f-4c3a-a7cc-0d7eff235663",
  "type": "TRAINING.CLOSE",
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
Type of operation: `TRAINING.CLOSE` — Close a training pool. ||
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