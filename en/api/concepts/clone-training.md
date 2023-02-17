# Clone a training pool

{% include [announce](../_includes/announce.md) %}

Creates a duplicate training pool.

An empty training pool will be created with the same parameters.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/trainings/<training_id>/clone
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/trainings/<training_id>/clone
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

```json
{
  "id": "7ea08f99-5e24-47b4-b61f-c177a868d801",
  "type": "TRAINING.CLONE",
  "status": "SUCCESS",
  "submitted": "2021-02-26T10:13:32.921",
  "started": "2021-02-26T10:13:32.921",
  "finished": "2021-02-26T10:13:32.921",
  "progress": 100,
  "parameters": {
    "training_id": "123456"
  },
  "details": {
    "training_id": "123457"
  }
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**

Operation ID. ||
|| **type** | **string**

Type of operation: `TRAINING.CLONE` — Clone a training pool. ||
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

ID of the source training pool. ||
|| **details.training_id** | **string**

ID of the new training pool. ||
|#

{% include [contact-support](../../guide/_includes/contact-support.md) %}