# Get aggregate responses

{% include [announce](../_includes/announce.md) %}

Gets aggregated responses.

{% note alert "Restriction" %}

You can send a maximum of 5 requests of this kind per minute, 30 requests per hour, and 200 requests per day. Refer to the [Rate limiting](rate-limiting.md) section for the complete list of the request limitations in Toloka API.

{% endnote %}

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/aggregated-solutions/<operation_id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/aggregated-solutions/<operation_id>
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

## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **sort** | **string**

Parameters for sorting in ascending order:

- `task_id` — Task ID.

To change the sorting direction to descending, add a hyphen before the parameter: `sort=-task_id`. ||
|| **Standard query parameters** | [limit](./standard-query-parameters.md#limit), [task_id_gt](./standard-query-parameters.md#task_id_gt), [task_id_gte](./standard-query-parameters.md#task_id_gte), [task_id_lt](./standard-query-parameters.md#task_id_lt), [task_id_lte](./standard-query-parameters.md#task_id_lte). ||
|#

## Query example {#request-example}

You can set up the display of the list of responses in parts (for example, 10 responses at a time):

1. Show the first 10 responses, starting with the response with the lowest task ID.
1. Show the remaining responses (10 at a time) in ascending order.

**Show the first 10 responses**

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/aggregated-solutions/<operation_id>?sort=task_id&limit=10
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/aggregated-solutions/<operation_id>?sort=task_id&limit=10
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

**Show the remaining tasks sorted by ascending ID**

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/aggregated-solutions/<operation_id>?sort=task_id&limit=10&task_id_gt=<ID of the last task from the previous response>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/aggregated-solutions/<operation_id>?sort=task_id&limit=10&task_id_gt=<ID of the last task from the previous response>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Response {#response}

[Aggregation result](aggregate-by-task.md) in the `items` array.

```json
{"items" : [{task #1}, {task #2}, ... {task #n}], "has_more": true}
```

{% include [contact-support](../../guide/_includes/contact-support.md) %}