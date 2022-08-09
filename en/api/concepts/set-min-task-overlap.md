# Stop assigning a task

{% include [announce](../_includes/announce.md) %}

Stops assigning a task to Tolokers.

Set the `overlap` field to `0`. For tasks with infinite overlap, change the value of `infinite_overlap` to `false`.

## Request {#request}

{% list tabs %}

- Sandbox

    ```bash
    PATCH https://sandbox.toloka.dev/api/v1/tasks/<task_id>/set-overlap-or-min
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Production version

    ```bash
    PATCH https://toloka.dev/api/v1/tasks/<task_id>/set-overlap-or-min
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
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
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

```json
{
  "overlap": 0,
  "infinite_overlap": false
}
```

## Response {#response}

Contains [task data in JSON format](create-task.md#body).