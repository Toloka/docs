# Create multiple task suites

Creates multiple task suites.

{% note alert %}

You can add a maximum of 100,000 tasks per minute and a maximum of 2,000,000 tasks per day.

{% endnote %}

You can add a maximum of 100,000 tasks per minute and a maximum of 2,000,000 tasks per day.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.yandex.com/api/v1/task-suites
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    [{task suite 1}, {task suite 2},... {task suite N}]
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.yandex.com/api/v1/task-suites
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    [{task suite 1}, {task suite 2},... {task suite N}]
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix. ||
**Content-Type** | Specifies the data format in the request body.

## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **async_mode** {#async_mode} | **boolean**

Mode for request processing:

- `true` — Asynchronous. Creates an asynchronous operation that runs in the background. The [response](#response) contains information about the operation (start and  completion time, status).
- `false` — Synchronous. The [response](#response) contains information about one or multiple task suites created.

The default value is `false`. ||
|| **allow_defaults** | **boolean**

Overlap settings:

- `true` — Use the overlap that is set in the pool parameters (in the [defaults.default_overlap_for_new_task_suites](create-pool.md#default_overlap_for_new_task_suites) key).
- `false` — Use the overlap that is set in the task suite parameters (in the [overlap](create-task-suite.md#overlap) field).

The default value is `false`. ||
|| **skip_invalid_items** | **boolean**

Validation parameters for JSON objects:

- `true` — Create the task suites that passed validation.
- `false` — If at least one of the task suites didn't pass validation, stop the operation and don't create the task suites.

The default value is `false`. ||
|| **open_pool** | **boolean**

Open the pool immediately after the operation is completed, if the pool is closed. The default value is `false`. ||
|| **operation_id** | **string**

Operation ID for asynchronously loading one or more task suites (if `async_mode=true`).

We recommend sending the ID in the POST request to avoid accidental errors, such as creating the operation multiple times for the same task suites.

The ID should conform to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122).

You can use this ID in the future to [get information about the operation](operations.md). ||
|#

## Response {#response}

The response format depends on the value of [async_mode](#async_mode).

{% list tabs %}

- The task suites (async_mode=false)

    ```json
    {
      "items": {
        "0": {<task suite>},
        "2": {<task suite>}, ...
        "<n>": {<task suite N>}
      },
      "validation_errors": {
        "1": {<validation errors for the task suite>},
        "3": {<validation errors for the task suite>}, ...
        "<n>": {<validation errors for task suite N>}
      }
    }
    ```

    #|
    || Parameter | Overview ||
    || **items** | **object**

    An object with the created task suites. ||
    || **validation_errors** | **object**

    An object with the errors in task suites. Returned if the request has the parameter `skip_invalid_items=true`. ||
    || **\<n\>** | **object**

    Sequential number of the task suite in the array (starting from 0). ||
    |#

- Information about the operation (async_mode=true)

    ```json
    {
      "id": "26e130ad3652443a3dc5094791e48ef9",
      "type": "TASK_SUITE.BATCH.CREATE",
      "status": "FAIL",
      "submitted": "2015-12-13T23:32:01",
      "started": "2015-12-13T23:33:00",
      "finished": "2015-12-13T23:34:12",
      "details": {
        "success_count": 0,
        "failed_count": 2
      }
    }
    ```

    #|
    || Parameter | Overview ||
    || **id** | **string**

    Operation ID. ||
    || **type** | **string**

    Operation type:

    - `POOL.OPEN` — Opening a pool.
    - `POOL.CLOSE` — Closing a pool.
    - `PROJECT.ARCHIVE` — Archiving a project.
    - `POOL.ARCHIVE` — Archiving a pool.
    - `TASK_SUITE.BATCH_CREATE` — Creating multiple task suites. ||
    || **status** | **string**

    The status of the operation:

    - `PENDING` — Not started yet.
    - `RUNNING` — In progress.
    - `SUCCESS` — Completed successfully.
    - `FAIL` — Not completed. ||
    || **submitted** | **string**

    The UTC date and time the request was sent, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
    || **started** | **string**

    The UTC date and time the operation started, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
    || **finished** | **string**

    The UTC date and time the operation was completed, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
    || **details. success_count** | **integer**

    The number of task suites uploaded. ||
    || **details. failed_count** | **integer**

    The number of task suites that didn't upload. ||
    |#

{% endlist %}