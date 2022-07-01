# Get the list of operations

Gets the list of operations.

## Request {#query}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.yandex.com/api/v1/operations
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.yandex.com/api/v1/operations
    Authorization: OAuth <OAuth token>
    ```
{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **type** | **string**

Operation type:

- `POOL.OPEN` — Opening a pool.

- `POOL.CLOSE` — Closing a pool.

- `PROJECT.ARCHIVE` — Archiving a project.

- `POOL.ARCHIVE` — Archiving a pool.

- `TASK_SUITE.BATCH_CREATE` — Creating multiple task suites.

- `KNOWN_SOLUTIONS.GENERATE` — Generating control tasks. ||
|| **status** | **string**

The status of the operation:

- `PENDING` — Not started yet.

- `RUNNING` — In progress.

- `SUCCESS` — Completed successfully.

- `FAIL` — Not completed. ||
|| **sort** | **string**

Parameters to sort by:

- `id` — Operation ID.

- `submitted` — The UTC date and time when the request was sent, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss].

- `finished` — The UTC date and time when the operation was finished, in ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss].


To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **Standard query parameters** |
[limit](./standard-query-parameters.md#limit), [id_gt](./standard-query-parameters.md#id_gt), [id_gte](./standard-query-parameters.md#id_gte), [id_lt](./standard-query-parameters.md#id_lt), [id_lte](./standard-query-parameters.md#id_lte), [submitted_gt](./standard-query-parameters.md#submitted_gt), [submitted_gte](./standard-query-parameters.md#submitted_gte), [submitted_lt](./standard-query-parameters.md#submitted_lt), [submitted_lte](./standard-query-parameters.md#submitted_lte), [finished_gt](./standard-query-parameters.md#finished_gt), [finished_gte](./standard-query-parameters.md#finished_gte), [finished_lt](./standard-query-parameters.md#finished_lt), [finished_lte](./standard-query-parameters.md#finished_lte).
||
|#

## Response {#response}

Contains a list of operations in the `items` array:

```json
{"items": [{operation details 1}, {operation details 2}, ... {operation details n}], "has_more": false}
```
