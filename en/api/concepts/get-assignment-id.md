# Get response properties

Gets the properties of a response.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.yandex.com/api/v1/assignments/<response_id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.yandex.com/api/v1/assignments/<response_id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**response_id** | ID of the task suite assignment to a Toloker.


## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Response {#response}

```json
{
  {
    "id": "0000082301--5f69bcc046757f5cf86c12ff",
    "task_suite_id": "0000082301--5f69bc8446757f5cf86c0e24",
    "pool_id": "533249",
    "user_id": "b4d8bcc33403cae9eb69991c8bb90bdc",
    "status": "ACCEPTED",
    "reward": 0.01,
    "bonus_ids": "IDs of the rewards given for the task",
    "tasks": [{
        "id": "6946cefa-32af-4f62-b530-8d2c71fa2966",
        "input_values": {
            "image": "http://images.com/1.png"
        }
    }],
    "solutions": [{
        "output_values": {
            "result": "OK"
        }
    }],
    "mixed": false,
    "automerged": false,
    "created": "2020-09-22T08:58:40.913",
    "submitted": "2020-09-22T08:58:46.207",
    "accepted": "2020-09-22T08:58:46.207",
    "public_comment": "Well done!",
    "owner": {
      "id": "ac1e4701364b4ccef8a4fe10a8980cff",
      "myself": true
    }
  }
}
```

#|
|| Parameter | Overview ||
|| **id** | **string**
ID of the task suite assignment to a Toloker. ||
|| **task_suite_id** | **string**

ID of a task suite. ||
|| **pool_id** | **string**

ID of the pool that the task suite belongs to. ||
|| **user_id** | **string**

ID of the Toloker who was assigned the task suite. ||
|| **status** | **string**

Status of an assigned task suite:

- `ACTIVE` — Being completed by a Toloker.

- `SUBMITTED` — Completed but not checked.

- `ACCEPTED` — Accepted by the requester.

- `REJECTED` — Rejected by the requester.

- `SKIPPED` — Skipped by the Toloker.

- `EXPIRED` — The time for completing the tasks expired. ||
|| **reward** | **integer**

Payment received by the Toloker. ||
|| **public_comment** | **string**

A comment for the Toloker.

Maximum length: 2048 characters. ||
|| **bonus_ids[]** | **array of strings**

`IDs` of rewards issued for the task. ||
|| **tasks[]** | **array of objects**

[Data for the tasks](task-suite.md). ||
|| **first_declined_ solution_attempt[]** | **array of objects**

For training tasks. The Toloker's first responses in the training task (only if these were the wrong answers). If the Toloker answered correctly on the first try, the `first_declined_solution_attempt` array is omitted.

Arrays with the responses (`output_values`) are arranged in the same order as the task data in the `tasks` array.
```json
{
       "output_values": {
         "<field 1>": <response>,
         "<field 2>": <response>
...
         "<field N>": <response>
       },
...
}
```
||
|| **solutions[]** | **array of objects**
Toloker responses. Arranged in the same order as the data for tasks in the `tasks` array.

```json
{
       "output_values": {
         "<field 1>": <response>,
         "<field 2>": <response>
...
         "<field N>": <response>
       },
...
}
```
||
|| **mixed** | **boolean**

Type of operation for creating a task suite:

- `true` — Automatic ("smart mixing").

- — Manually.


The default value is `false`.

For more information about creating task suites, see the [Requester's guide](https://toloka.ai/docs/guide/concepts/pool-main.html?lang=en). ||
|| **automerged** | **boolean**

Flag of the response received as a result of [merging identical tasks](tasks.md#task-merge). Value:

- `true` — The response was recorded when identical tasks were merged.
- `false` — Normal Toloker response. ||
|| **created** | **string**

The date and time when the task suite was assigned to a Toloker. The date is specified in UTC in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **submitted** | **string**

The date and time when the task suite was completed by a Toloker. The date is specified in UTC in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **accepted** | **string**

The date and time when the responses for the task suite were accepted by the requester. The date is specified in UTC in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **rejected** | **string**

The date and time when the responses for the task suite were rejected by the requester. The date is specified in UTC in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **skipped** | **string**

The date and time when the task suite was skipped by a Toloker. The date is specified in UTC in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **expired** | **string**

The date and time when the task suite expired. The date is specified in UTC in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **owner.id** | **string**

Requester ID. ||
|| **owner.myself** | **boolean**

Checks who the object belongs to:

- `true` — The Toloker whose OAuth token is specified in the request.
- `false` — Another account (employee or owner).

{% if audience == "internal" %}

**owner.company_id** | **string**

The requester's company ID.

{% endif %}

||
|#
