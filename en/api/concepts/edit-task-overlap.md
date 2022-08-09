# Edit a task

{% include [announce](../_includes/announce.md) %}

Changes the task overlap.

You can:

- Set a [numeric value](create-task.md#overlap) or an [infinite overlap](create-task.md#infinite) to assign a task to all Tolokers (for example, for training tasks).

- Add preliminary responses or change [their values](create-task.md#baseline) if they were set.

    Preliminary responses are used to calculate  response confidence when dynamic overlap (incremental relabeling, IRL) is enabled.

- Make [control](../../glossary.md#control) and [training](../../glossary.md#training-tasks) tasks from regular ones or edit [responses](create-task.md#known) and [hints](create-task.md#message) for existing tasks.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    PATCH https://toloka.dev/api/v1/tasks/<task_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    PATCH https://sandbox.toloka.dev/api/v1/tasks/<task ID>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**task_id** | Task ID.

## Request body {#body}

#### Numeric overlap value

```json
{
  "overlap": <new overlap value>,
  "infinite_overlap": false
}
```

#### Infinite overlap

```json
{
  "overlap": null,
  "infinite_overlap": true
}
```

#### Preliminary responses

```json
{
  "baseline_solutions":[
    {
      "output_values":{<output data values>},
      "confidence_weight":<from 0 to 1>
    }
  ]
}
```

#### Responses and hints for control tasks and training tasks

```json
{
  "known_solutions":[
    {
      "output_values":{<output data values>},
      "correctness_weight":<from 0 to 1>
    }
  ],
  "message_on_unknown_solution": <message string>
}
```

## Response {#response}

Contains [task data in JSON format](create-task.md#body).