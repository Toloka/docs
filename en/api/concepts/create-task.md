# Create one or multiple tasks

Creates one or multiple tasks.

You can add a maximum of 100,000 tasks per minute and a maximum of 2,000,000 tasks per day.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.yandex.com/api/v1/tasks
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    // one task {task data}

    // or multiple tasks [{task 1}, {task 2},... {task n}]
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.yandex.com/api/v1/tasks
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    // one task {task data}

    // or multiple tasks [{task 1}, {task 2},... {task n}]
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

## Request body {#body}

```json
{
  "pool_id": "1",
  "input_values": {
    "image_url": "www.images/image1.ru"
  },
  "known_solutions": [
    {
      "output_values": {
        "result": "OK",
        "like": false
      },
      "correctness_weight": 0.8
    },
    {
      "output_values": {
        "result": "OK",
        "like": true
      },
      "correctness_weight": 1
    }
  ],
  "baseline_solutions": [
    {
      "output_values": {
        "result": "OK",
        "like": false
      },
      "confidence_weight": 0.8
    },
    {
      "output_values": {
        "result": "OK",
        "like": true
      },
      "confidence_weight": 1
    }
  ],
  "message_on_unknown_solution": "The cat is in a good mood.",
  "overlap": 3,
  "infinite_overlap": false,
  "reserved_for": [],
  "unavailable_for": []
}
```

#|
|| Key | Overview ||
|| **pool_id** | **string \| required**

ID of the pool that the task is uploaded to. ||
|| **input_values** | **object \| required**

Input data for a task. List of pairs:

```json
  "<ID of field 1>": "<value of field 1>",
  "<ID of field 2>": "<value of field 2>",
  ...
  "<ID of field N>": "<value of field N>"
```
||
|| **known_solutions[].output_values** | **object \| required**

Output data values to check. You should specify values for all required output data fields.

```json
  "<ID of field 1>": "<correct response>",
  "<ID of field 2>": "<correct response>",
  ...
```
||
|| **baseline_solutions[].output_values** | **object \| required**

Output data values for preliminary responses.

```json
  "<ID of field 1>": "<preliminary response>",
  "<ID of field 2>": "<preliminary response>",
  ...
```
||
|| **baseline_solutions[].confidence_weight** | **float \| required**

Confidence in a response, from 0 to 1.
The default value is 1. ||
|| **overlap** {#overlap} | **string \| required if**

Required if the `allow_defaults=true` parameter is not used when creating tasks and the overlap is not specified in the pool parameters (the [defaults.default_overlap_for_new_tasks](create-pool.md#default-overlap-tasks) key).

Task overlap. ||
|| **known_solutions[]** {#known} | **array of objects**

Correct responses to [control](../../glossary.md#control) and [training](../../glossary.md#training-tasks) tasks.

You can specify several options for a correct task response.

If one option is more correct than another, you can assign different weights to the response options. To do this, use the `correctness_weight` key. ||
|| **known_solutions[].correctness_weight** | **float**

The weight of a correct response in the range from 0 to 1.

Lets you count a response as partially correct. This is convenient when there is no single right response to the task.

This works like awarding points: if you need to complete one control task correctly to get a skill (receive 1 point), you may complete one task with a weight of 1 or two tasks with a weight of 0.5 or higher.

The default value is 1. ||
|| **baseline_solutions[]** {#baseline} | **array of objects**

Preliminary responses. This data simulates Toloker responses when calculating `confidence` in a response. It is used in dynamic overlap (also known as incremental relabeling or IRL) and aggregation of results by skill.

Define `output_values` and `confidence_weight` for each preliminary response.

For example, you ask Tolokers to label whether an image shows a cat or a dog. Suppose your neural network already determined that the image might show a dog with a probability of 80% and a cat with a probability of 40%. Let's say you set dynamic overlap from 1 to 3 and the minimum response confidence at 85%.

If the Toloker answers "Dog" and the confidence in their response is high, the overlap most likely won't increase because one response is enough. If the Toloker answers "Cat", the confidence is most likely not high enough and the overlap will increase further.

Can't be used when creating a task suite: an error with code 400 saying `VALUE_NOT_ALLOWED` will be returned to your request. ||
|| **message_on_unknown_solution** {#message} | **string**

Hint for the task (for training tasks). ||
|| **infinite_overlap** {#infinite} | **boolean**

Assigns tasks with infinite overlap. For instance, you can use this for training tasks when you want to assign them to all Tolokers:

- `true` — Use infinite overlap.
- `false` — Use the overlap that is set for the task or pool.

The default value is `false`. ||
|| **origin_task_id** | **string**

ID of the task it was copied from. ||
|| **reserved_for[]** | **array of integer**

IDs of Tolokers who will have access to the task. ||
|| **unavailable_for[]** | **array of integer**

IDs of Tolokers who shouldn't have access to the task. ||
|#

## Response {#response}

{% cut "One task" %}

Depending on the [async_mode](#async_mode) value in the request, the response contains:

{% list tabs %}

- Task data(`async_mode=false`)

  Information about the created task. Besides [parameters](#body) that are set when creating a task, it includes parameters that are assigned to the task automatically:

  #|
  || Parameter | Overview ||
  || **id** | **string**

  Task ID. ||
  || **origin_task_id** | **string**

  The ID of a task from another pool from which this task was copied for majority vote verification. ||
  || **created** | **string**

  The UTC date and time when the task suite was created, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
  |#

- Information about the operation (`async_mode=true`)

    ```json
    {
      "id": "2ed92b7f-75c0-4771-ae2f-3911232d6d4e",
      "type": "TASK.BATCH_CREATE",
      "status": "RUNNING",
      "submitted": "2020-12-23T16:26:20.131",
      "progress": 0,
      "parameters": {
        "open_pool": false,
        "allow_defaults": false,
        "skip_invalid_items": false
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
  || **progress** | **integer**

  The percentage of the operation completed. ||
  || **parameters** | **object**

  Operation parameters (depending on the operation type). ||
  || **parameters.open_pool** | **boolean**

  Open the pool immediately after creating the tasks, if the pool is closed. The default value is `false`. ||
  || **parameters.allow_defaults** | **boolean**

  Overlap settings:

  - `true` — Use the overlap that is set in the pool parameters (in the [defaults.default_overlap_for_new_tasks](create-pool.md#default-overlap-tasks) key).
  - `false` — Use the overlap that is set in the task parameters (in the [overlap](#overlap) field).

  The default value is `false`. ||
  || **parameters.skip_invalid_items** | **boolean**

  Validation parameters for JSON objects:

  - `true` — Create the tasks that passed validation. Skip the rest of the tasks (errors will be listed in the response to the request).
  - `false` — If one or more tasks didn't pass validation, stop the operation and don't create any tasks.

  The default value is `false`. ||
  |#

{% endlist %}

{% endcut %}

{% cut "Multiple tasks" %}

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