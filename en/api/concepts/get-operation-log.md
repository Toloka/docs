# Get the operation log

{% include [announce](../_includes/announce.md) %}

Gets the operation log.

You can get logs for asynchronous operations (`async_mode = true`). Such operations run in the background.

Logs are available only for the last month. To get the logs for an earlier period, contact [support](../../guide/troubleshooting/troubleshooting.md).

You can get the operation log:

- When you create [one or multiple](create-task.md) tasks.
- When you create [one or multiple](create-task-suite.md) task suites.
- [When issuing rewards](create-bonus.md) to Tolokers.

If the operation was successful, the log contains `IDs` of the created objects, otherwise it contains the details of validation errors.

## Request {#request}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/operations/<operation_id>/log
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/operations/<operation_id>/log
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

Contains a JSON array describing each step of the operation.

```json
[
  {
    "type": <action type>,
    "success": <true/false>,
    "input": {
      <input values at the operation step>
    },
    "output": {
      <output values at the operation step or error details>
    }
  },
  ...
]
```

#|
|| Parameter | Overview ||
|| **type** | **string**

Type of operation step. It depends on:

- Type of operation for which the log is requested.
- Execution result (`success: true/false`).

The `type` values for a successful asynchronous operation:

- `USER_BONUS_PERSIST` — Issuing a reward.
- `TASK_CREATE` — Creating a task.
- `TASK_SUITE_CREATE` — Creating a task suite.

The `type` values for a failed asynchronous operation:

- `USER_BONUS_VALIDATE` — Issuing a reward.
- `TASK_VALIDATE` — Creating a task.
- `TASK_SUITE_VALIDATE` — Creating a task suite.

The type of operation step determines the `input` and `output` values. ||
|| **success** | **boolean**

Step result:

- `true` — Completed successfully.
- `false` — Not completed. ||
|| **input** | **JSON**

The data in the `input` is copied from the input data passed when creating the operation. ||
|| **output** | **JSON**

Output values at the operation step.

The data in the `output` for a successful operation:

- For the action `USER_BONUS_PERSIST` — `user_bonus_id` (the `ID` of the issued reward).
- For the action `TASK_CREATE` — `task_id` (the `ID` of the created task).
- For the action `TASK_SUITE_CREATE` — `task_suite_id` (the `ID` of the created task suite).

Data in the `output` for a failed operation:

- `code` — Name of the error.
- `message` — Explanation of how to fix the error.
- `payload` — Specifies the error reason if `code = VALIDATION_ERROR`.||
|#

{% cut "Example of a log when a reward was issued successfully" %}

```json
[
  {
    "type": "USER_BONUS_PERSIST",
    "success": true,
    "input": {
      "id": 65,
      "amount": 1.5,
      "created": "2021-02-02T12:51:00",
      "user_id": "ec00d2407f7241258d0faba610110d95",
      "public_title": {
        "EN": "Good job!",
        "RU": "Молодец!"
      },
      "public_message": {
        "EN": "Ten tasks completed",
        "RU": "Выполнено 10 заданий"
      },
      "private_comment": "pool_123456",
      "without_message": false
    },
    "output": {
      "user_bonus_id": "2128"
    }
  }
]
```

{% endcut %}

{% cut "Example of a log when issuing a reward failed" %}

```json
[
  {
    "type": "USER_BONUS_VALIDATE",
    "success": false,
    "input": {
      "id": 65,
      "amount": 1.5,
      "created": "2021-02-02T12:51:00",
      "user_id": "ec00d2407f7241258d0faba610110d95",
      "public_title": {
        "EN": "Good job!",
        "RU": "Молодец!"
      },
      "public_message": {
        "EN": "Ten tasks completed",
        "RU": "Выполнено 10 заданий"
      },
      "private_comment": "pool_123456",
      "without_message": false
   },
    "output": {
      "user_id": {
        "code": "ENTITY_DOES_NOT_EXIST",
        "message": "Entity does not exist"
      }
    }
  }
]
```

{% endcut %}

{% include [contact-support](../../guide/_includes/contact-support.md) %}