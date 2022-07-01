# Move a pool to the archive

Moves a pool to the archive.

If a pool isn't in use, it can be moved to the archive. The pool must have the "closed" status.

A pool with rejected tasks can be archived 9 days after the last task was rejected. This period is required to review the results if the Toloker submits an appeal.

Exams with automatic acceptance by accuracy, where tasks with insufficient accuracy are rejected, can also be archived in 9 days.

## Request {#request}

{% list tabs %}

- Production version

  ```bash
  POST https://toloka.yandex.com/api/v1/pools/<pool_id>/archive
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  POST https://sandbox.toloka.yandex.com/api/v1/pools/<pool_id>/archive
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

If the pool is already archived, attempting to archive it again returns an empty response with status 204.

{% endnote %}


Contains information about the results of the operation.

```json
{
  "id" : "57068577e4b0bf7b07a0256f",
  "type" : "POOL.ARCHIVE",
  "status" : "SUCCESS",
  "submitted" : "2016-04-07T16:06:15.902",
  "started" : "2016-04-07T16:06:15.902",
  "finished" : "2016-04-07T16:06:15.902",
  "progress" : 100,
  "parameters" : {
    "pool_id" : "1"
  }
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**

User ID. ||
|| **type** | **string**

Type of operation: `POOL.ARCHIVE` — Archiving a pool. ||
|| **status** | **string**

The status of the operation:

- `PENDING` — Not started yet.
- `RUNNING` — In progress.
- `SUCCESS` — Completed successfully.
- `FAIL` — Not completed. ||
|| **submitted** | **string**

The UTC date and time the request was sent, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **started** | **string**

The UTC date and time the operation started, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **finished** | **string**
The UTC date and time the operation was completed, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **progress** | **integer**
The percentage of the operation completed. ||
|| **parameters.pool_id** | **string**
Pool ID. ||
|#
