# Create multiple tasks

{% include [announce](../_includes/announce.md) %}

Creates multiple tasks.

You can add a maximum of 100,000 tasks per minute and a maximum of 2,000,000 tasks per day.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/tasks
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    [{task 1}, {task 2},... {task n}]
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/tasks
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    [{task 1}, {task 2},... {task n}]
    ```

{% endlist %}

## Headers {#headers}

#|
|| Title | Overview ||
|| **Authorization** | A token for account authorization. Add OAuth as a prefix. ||
|| **Content-Type** | Specifies the data format in the request body. ||
|#

## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **async_mode** {#async_mode} | **boolean**

Mode for request processing:

- `true` — Asynchronous. Creates an asynchronous operation that runs in the background. The response contains information about the operation (start and completion time, status, number of task suites).
- `false` — Synchronous. The response contains information about one or more created tasks. Maximum of 5000 tasks per request.

The default value is `false`. ||
|| **allow_defaults** | **boolean**

Overlap settings:

- `true` — Use the overlap that is set in the pool parameters (in the [defaults.default_overlap_for_new_tasks](create-pool.md#default-overlap-tasks) key).
- `false` — Use the overlap that is set in the task parameters (in the [overlap](#overlap) field).

The default value is `false`. ||
|| **skip_invalid_items** | **boolean**

Validation parameters for JSON objects:

- `true` — Create the tasks that passed validation. Skip the rest of the tasks (errors will be listed in the response to the request).
- `false` — If one or more tasks didn't pass validation, stop the operation and don't create any tasks.

The default value is `false`. ||
|| **open_pool** | **boolean**

Open the pool immediately after the operation is completed, if the pool is closed. The default value is `false`. ||
|| **operation_id** | **string**

Operation ID for a scheduled upload of one or more tasks (if `async_mode=true` is set).

We recommended sending the ID in the POST request to avoid accidental errors, such as creating the operation multiple times for the same tasks.

The ID should conform to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122).

You can use this ID in the future to [get information about the operation](operations.md). ||
|#

## Response {#response}

Depending on the [async_mode](#async_mode) value in the request, the response contains:

{% list tabs %}

- Data for the tasks (`async_mode=false`)

    ```json
    {
      "items": {
        "0": {
          "id": "f432cac2-7184-47a3-8220-12ce362cb208",
          "pool_id": "21",
          "input_values": {
            "image": "http://images.com/1.png"
          },
          "overlap": 3,
          "created": "2016-09-29T18:04:00"
        }
      },
      "validation_errors": {
        "1": {
          "input_values.image": {
            "code": "VALUE_REQUIRED",
            "message": "Value must be present and not equal to null"
          }
        }
      }
    }
    ```

  #|
  || Parameter | Overview ||
  || **items** | **object**

  An object with the created tasks. ||
  || **\<n\>** | **object**

  Sequential number of the task in the array when created (starting from 0). ||
  || **id** | **string**

  Task ID. ||
  || **pool_id** | **string**

  The ID of the pool that the task is uploaded to. ||
  || **overlap** | **string**

  Task suite overlap. ||
  || **created** | **string**

  The UTC date and time when the task suite was created, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
  || **validation_errors** | **object**

  An object with errors in tasks. Returned if the request has the parameter `skip_invalid_items=true`. ||
  |#

- Information about the operation (`async_mode=true`)

    ```json
    {
      "id": "26e130ad3652443a3dc5094791e48ef9",
      "type": "TASK.BATCH_CREATE",
      "status": "FAIL",
      "submitted": "2015-12-13T23:32:01",
      "started": "2015-12-13T23:33:00",
      "finished": "2015-12-13T23:34:12",
      "parameters": {
        "allow_defaults": false,
        "skip_invalid_items": false,
        "open_pool": false
      },
      "details": {
        "total_count": 2,
        "valid_count": 1,
        "not_valid_count": 1,
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

  Type of operation: `TASK.BATCH_CREATE` — Creating multiple tasks. ||
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
  || **parameters.skip_invalid_items** | **boolean**

  Validation parameters for JSON objects:

  - `true` — Create the tasks that passed validation. Skip the rest of the tasks.
  - `false` — If one or more tasks didn't pass validation, stop the operation and don't create any tasks.

  The default value is `false`. ||
  || **details.total_count** | **string**

  The number of tasks in the request. ||
  || **details.valid_count** | **integer**

  The number of tasks that passed validation. ||
  || **details.not_valid_count** | **integer**

  The number of tasks that failed validation. ||
  || **details.success_count** | **integer**

  The number of tasks uploaded. ||
  || **details.failed_count** | **integer**

  The number of tasks that didn't upload. ||
  |#

{% endlist %}

{% endcut %}