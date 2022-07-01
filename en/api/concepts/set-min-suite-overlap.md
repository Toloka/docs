# Stop assigning a task suite

Stops assigning a task suite to Tolokers.

## Request {#request}

{% list tabs %}

- Production version

   ```bash
   PATCH https://toloka.yandex.com/api/v1/task-suites/<task_suite_id>/set-overlap-or-min
   Authorization: OAuth <OAuth token>
   Content-Type: application/JSON
   ```

- Sandbox

   ```bash
   PATCH https://sandbox.toloka.yandex.com/api/v1/task-suites/<task_suite_id>/set-overlap-or-min
   Authorization: OAuth <OAuth token>
   Content-Type: application/JSON
   ```
{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**task_suite_id** | ID of a task suite.


## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.


## Request body {#body}

```json
{
   "overlap": 0
}
```

#|
|| Parameter | Overview ||
|| **overlap** | **integer \| required if**

Required if the parameter is not used when creating a task suite `allow_defaults=true`, and the overlap is not specified in the pool parameters (in the [defaults.​default_​overlap_for_​new_task_suites](create-pool.md#default_overlap_for_new_task_suites)) key).

Task suite overlap. ||
|#

## Response {#response}

Contains the [task suite data in JSON format](create-task-suite.md#overlap).
