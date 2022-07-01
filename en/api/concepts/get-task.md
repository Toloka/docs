# Get a task

Gets task data.

## Request {#request}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.yandex.com/api/v1/tasks/<task_id>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/tasks/<task_id>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**task_id** | Task ID.


## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Response {#response}

Contains [task data in JSON format](create-task.md#body).
