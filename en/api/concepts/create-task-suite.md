# Create one or multiple task suites

Creates one or multiple task suites.

{% note alert %}

You can add a maximum of 100,000 tasks per minute and a maximum of 2,000,000 tasks per day.

{% endnote %}


## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.yandex.com/api/v1/task-suites
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    // one task suite {task suite parameters}

    // or multiple task suites [{task suite 1}, {task suite 2},... {task suite N}]
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.yandex.com/api/v1/task-suites
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    // one task suite {task suite parameters}

    // or multiple task suites [{task suite 1}, {task suite 2},... {task suite N}]
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

- `true` — Asynchronous. Creates an asynchronous operation that runs in the background. The response contains information about the operation (start and  completion time, status).

- `false` — Synchronous. The response contains information about one or multiple task suites created.


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

## Request body {#body}

```json
{
    "id": "63614047-38c3-4ad4-8a86-99c5c651a9b8",
    "pool_id": "1",
    "tasks": [
        {"id": "49a333ea-2728-4c1c-ab1f-8ab1bfe4ee7e",
         "origin_task_id": "e3da7fe1-828d-4d9c-b49d-42c0eb5fcfde",
         "input_values": {
                "image_url": "www.image1.ru"
            },
            "known_solutions": [
                {
                    "correctness_weight": 0.95,
                    "output_values": {
                        "colour": "black"
                    }
                },
                {
                    "correctness_weight": 0.7,
                    "output_values": {
                        "colour": "gray"
                    }
                }
            ],
            "message_on_unknown_solution": "The elephant is black"
        },
        {
            "input_values": {
                "image_url": "www.image2.ru"
            },
            "known_solutions": [
                {
                    "correctness_weight": 1,
                    "output_values": {
                        "colour": "white"
                    }
                }
            ],
            "message_on_unknown_solution": "The elephant is white"
        }
    ],
    "overlap": 5,
    "infinite_overlap": false,
    "remaining_overlap": 3,
    "reserved_for": [],
    "unavailable_for": [],
    "issuing_order_override": 3,
    "mixed": true,
    "automerged": false,
    "created": "2016-04-18T12:43:04.988"
}

```


#|
|| Parameter | Overview ||
|| **pool_id** | **string \| required**

The ID of the pool that tasks are uploaded to. ||
|| **tasks[]** | **array of object \| required**

Data for the tasks. ||
|| **tasks[].input_values** | **object \| required**

Input data for a task. List of pairs:

```json
    "<ID of field 1>": "<value of field 1>",
    "<ID of field 2>": "<value of field 2>",
    ...
    "<ID of field N>": "<value of field N>"
```
||
|| **overlap** {#overlap} | **integer \| required if**

Required if the parameter is not used when creating a task suite `allow_defaults=true`, and the overlap is not specified in the pool parameters (in the [defaults.​default_​overlap_for_​new_task_suites](create-pool.md#default_overlap_for_new_task_suites) key).

Task suite overlap. ||
|| **longitude** | **float \| required if**

Required if tasks are selected on the map. Otherwise, not used.

The longitude of the point on the map for the task suite. ||
|| **latitude** | **float \| required if**

Required if tasks are selected on the map. Otherwise, not used.

The latitude of the point on the map for the task suite. ||
|| **tasks[].known_solutions** | **object**

Responses and hints for control tasks and training tasks. ||
|| **tasks[].known_solutions.output_values** | **object**

Correct responses in a task (for control tasks). If multiple correct responses are possible, define `output_values` for each possible response and set the weight for the correct response (the `correctness_weight` key).

```json
    "<ID of field 1>": "<correct response>",
    "<ID of field 2>": "<correct response>",
    ...
    "<ID of field N>": "<correct response N>"
```
||
|| **tasks[].known_solutions.correctness_weight** | **float**

The weight of a correct response. Allows you to set multiple versions of correct responses and rank them by correctness. For example, if a correct response is weighted 0.5, it counts as half of a mistake for the Toloker. The more correct the response in `correctValues`, the higher its weight. ||
|| **tasks[].message_on_unknown_solution** | **string**

Hint for the task (for training tasks). ||
|| **infinite_overlap** | **boolean \| required**

Assigning a task suite with infinite overlap. This option is used, for instance, for suites of training tasks when you want to assign them to all Tolokers:
- `true` — Use infinite overlap.

- `false` — Use the overlap that is set for the task suite or pool. ||
|| **reserved_for[]** | **array of integer**

IDs of Tolokers who will have access to the task suites. ||
|| **unavailable_for[]** | **array of integer**

IDs of Tolokers who shouldn't have access to the task suite. ||
|| **issuing_order_override** | **float**

The priority of a task suite among other suites in the pool. Defines the order in which task suites are assigned to Tolokers. The larger the parameter value, the higher the priority.

This parameter can be used if the pool has `issue_task_suites_in_creation_order: true`.

Allowed values: from `-99999.99999` to `99999.99999`.

The default value is `0`. ||
|| **mixed** | **boolean**

Type of operation for creating a task suite:

- `true` — Automatically with the "smart mixing" option (for more information, see the [Requester's guide](https://toloka.ai/docs/guide/concepts/task_upload.html?lang=en)).

- — Manually.
||
|#


## Response {#response}

{% cut "One task suite" %}

It includes:

- [Task suite data](create-task-suite.md#body) in JSON format.
- Parameters that are assigned automatically.

#|
|| Parameter | Overview ||
|| **id** | **string**

ID of a task suite. ||
|| **tasks[].id** | **string**

Task ID if the task suite is created automatically with the "smart mixing" option (for more information, see the [Requester's guide](https://toloka.ai/docs/guide/concepts/task_upload.html?lang=en)). ||
|| **tasks[].origin_task_id** | **string**

The ID of a task from another pool from which this task was copied for majority vote verification.
{% if audience == "internal" %}**owner.company_id** | **string**

The requester's company ID.{% endif %} ||
|| **remaining_overlap** | **integer**

The remaining overlap for each task. For example, if the task has an overlap of `5` but was completed by two  people, the `remaining_overlap` value is `3`.

If the task is under review or active, the key is `0`. ||
|| **automerged** | **boolean**

Flag for whether a task suite is created after [merging tasks](create-prj.md#task-merge). Value:

- `true` — The task suite is generated as a result of merging identical tasks.
- `false` — A standard task suite created by "smart mixing" or by the requester. ||
|| **created** | **string**

The UTC date and time when the task suite was created, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||

|#

{% endcut %}

{% cut "Multiple task suites" %}

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

    The UTC date and time the request was sent, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
    || **started** | **string**

    The UTC date and time the operation started, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
    || **finished** | **string**

    The UTC date and time the operation was completed, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
    || **details. success_count** | **integer**

    The number of task suites uploaded. ||
    || **details. failed_count** | **integer**

    The number of task suites that didn't upload. ||
    |#

{% endlist %}

{% endcut %}