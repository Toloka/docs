# Get operation details

{% include [announce](../_includes/announce.md) %}

Gets operation details.

## Request {#query}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/operations/<operation_id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/operations/<operation_id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**operation_id** | Operation ID.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Response {#response}

Contains operation details in JSON format (see the example in the [Operations](operations.md) section).

```json
{
  "id" : "57068577e4b0bf7b07a0256f",
  "type" : "TASK_SUITE.BATCH_CREATE",
  "status" : "FAIL",
  "submitted" : "2016-04-07T16:06:15.902",
  "started" : "2016-04-07T16:06:15.902",
  "finished" : "2016-04-07T16:06:15.902",
  "progress" : 100,
  "parameters" : {
    "open_pool" : fase,
    "allow_defaults" : false,
    "skip_invalid_items" : false
  },
  "details" : {
    "total_count" : 2,
    "valid_count" : 0,
    "failed_count" : 2,
    "success_count" : 0,
    "not_valid_count" : 2
  }
}
```

#|
|| Parameter | Overview ||
|| **id** | **string \| required**

Operation ID. ||
|| **type** | **string \| required**

Operation type:

- `POOL.OPEN` — Opening a pool.
- `POOL.CLOSE` — Closing a pool.
- `PROJECT.ARCHIVE` — Archiving a project.
- `POOL.ARCHIVE` — Archiving a pool.
- `SOLUTION.AGGREGATE` — Aggregating responses.
- `TASK_SUITE.BATCH_CREATE` — Creating multiple task suites.
- `KNOWN_SOLUTIONS.GENERATE` — Generating control tasks.||
|| **status** | **string \| required**

The status of the operation:

- `PENDING` — Not started yet.
- `RUNNING` — In progress.
- `SUCCESS` — Completed successfully.
- `FAIL` — Not completed.

Displayed for all operations except poll creation.||
|| **submitted** | **string \| required**

The UTC date and time the request was sent, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **started** | **string**

The UTC date and time the operation started, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **finished** | **string**

The UTC date and time the operation finished, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **progress** | **integer**

The percentage of the operation completed. ||
|| **parameters** | **JSON**

Operation parameters (depending on the operation type). ||
|| **details** | **JSON**

Details of the operation completion. ||
|#

The response doesn't provide a detailed error description. If an error has occurred, [request the operation log](get-operation-log.md).