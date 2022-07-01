# Create a training pool

Creates a training pool (training).

The pool is automatically assigned an ID.

{% note alert %}

You can send a maximum of 20 requests of this kind per minute and 100 requests per day.

{% endnote %}


{% note info %}

Learn about creating a main pool in [Create a pool](create-pool.md).

{% endnote %}


## Request {#request}

{% list tabs %}

- Production version

  ```bash
  POST https://toloka.yandex.com/api/v1/trainings
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

- Sandbox

  ```bash
  POST https://sandbox.toloka.yandex.com/api/v1/trainings
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.


## Request body {#body}

```json
{
  "project_id": "654321",
  "private_name": "Selection for a labeling task",
  "inherited_instructions": false,
  "public_instructions": "Unpaid selection for a project: 10 tasks, 90% threshold.",
  "may_contain_adult_content": false,
  "assignment_max_duration_seconds": 600,
  "mix_tasks_in_creation_order": true,
  "shuffle_tasks_in_task_suite": true,
  "training_tasks_in_task_suite_count": 10,
  "task_suites_required_to_pass": 1,
  "retry_training_after_days": 7
}
```

#|
|| Parameter {#training-param} | Overview ||
|| **project_id** | **string \| required**

ID of the project that the training pool was created for. ||
|| **private_name** | **string \| required**

Name of the training pool (only visible to the requester). ||
|| **inherited_instructions** | **boolean \| required**

Indicates whether to use the project instructions. To provide separate instructions for the training, enter it in `public_instructions`.

The default value is `false`. ||
|| **may_contain_adult_content** | **boolean \| required**

Whether the tasks contain adult content. ||
|| **training_tasks_in_task_ suite_count** | **integer \| required**
Number of training tasks per suite. ||
|| **task_suites_required_to_ pass** | **integer**

Number of task suites the Toloker needs to complete to get a skill and access the general tasks. ||
|| **public_instructions** | **string**

Instructions for completing a training task. You can use any HTML markup. ||
|| **assignment_max_duration_ seconds** | **integer**
The time allowed for completing a task suite, in seconds. We recommend allowing no more than 60 seconds per task suite (including the time for loading the page and submitting responses). ||
|| **mix_tasks_in_creation_ order** | **boolean**
Whether training tasks are issued in their upload order:
- `true` — Tasks are grouped into task suites in the order of rows in the uploaded file (top-to-bottom).
- `false` — Tasks are taken at random.
The default value is `true`. ||
|| **shuffle_tasks_in_task_suite** | **boolean**
Whether training tasks are shuffled within each task suite:
- `true` — Yes.
- `false` — No, they are listed in their upload order.
The default value is `true`. ||
|| **retry_training_after_days** | **integer**

Number of days until retry becomes available. ||
|#

## Response {#response}

Contains information about the created training pool.

```json
{
  "id": "123456",
  "project_id": "654321",
  "private_name": "Selection for a labeling task",
  "inherited_instructions": false,
  "public_instructions": "Unpaid selection for a project: 10 tasks, 90% threshold.",
  "may_contain_adult_content": false,
  "assignment_max_duration_seconds": 600,
  "mix_tasks_in_creation_order": true,
  "shuffle_tasks_in_task_suite": true,
  "training_tasks_in_task_suite_count": 10,
  "task_suites_required_to_pass": 1,
  "retry_training_after_days": 7,
  "owner": {
    "id": "ec00d2407f7241258d0faba610110d95",
    "myself": true
  },
  "status": "CLOSED",
  "created": "2021-02-24T18:12:57.962"
}
```

Besides [parameters that are set when creating a training pool,](#training-param) it includes parameters that are assigned to the pool automatically:

#|
|| Parameter | Overview ||
|| **id** | **string**

ID of the training pool. ||
|| **owner.id** | **string**

Requester ID. ||
|| **owner.myself** | **boolean**
Checks who the object belongs to:
- `true` — The user who made the request.
- `false` — Another account (employee or owner). ||
|| **status** | **string**
Training pool status:
- `OPEN` — Open.
- `CLOSED` — Closed.
- `ARCHIVED` — Archived. ||
|| **created** | **string**

The UTC date and time when the training pool was created, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|#
