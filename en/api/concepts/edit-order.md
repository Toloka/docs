# Change task suite priority

{% include [announce](../_includes/announce.md) %}

Changes the priority of a task suite in the pool.

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#patch-/task-suites/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

    ```bash
    PATCH https://toloka.dev/api/v1/task-suites/<task_suite_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    PATCH https://sandbox.toloka.dev/api/v1/task-suites/<task_suite_id>
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

## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **open_pool** | **boolean**

Open the pool immediately after the operation is completed, if the pool is closed. The default value is `false`. ||
|#

## Request body {#body}

```json
{
  "issuing_order_override": <new value>
}
```

#|
|| Parameter | Overview ||
|| **issuing_order_override** | **float**

The priority of a task suite among other suites in the pool. Defines the order in which task suites are assigned to Tolokers. The larger the parameter value, the higher the priority.

This parameter can be used if the pool has `issue_task_suites_in_creation_order: true`.

Allowed values: from `-99999.99999` to `99999.99999`.

The default value is `0`. ||
|#

## Response {#response}

Contains a [task suite in JSON format](task-suite.md).

{% include [contact-support](../../guide/_includes/contact-support.md) %}