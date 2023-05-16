# Change the task suite overlap

{% include [announce](../_includes/announce.md) %}

Changes the task suite overlap.

You can specify a [numeric value](#number_overlap) or set [infinite overlap](#infinite) to assign the task suite to all Tolokers (this is useful for training tasks).

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

Parameter | Overview
----- | -----
**open_pool** | **boolean**

Open the pool immediately after the operation is completed, if the pool is closed. The default value is `false`.

## Request body {#body}

#### Numeric overlap value {#number_overlap}

```json
{
  "overlap": <new overlap value>,
  "infinite_overlap": false
}
```

#### Infinite overlap {#infinite}

```json
{
  "overlap": null,
  "infinite_overlap": true
}
```

#|
|| Parameter | Overview ||
|| **overlap** | **integer \| required if**

Required if the parameter is not used when creating a task suite `allow_defaults=true`, and the overlap is not specified in the pool parameters (in the [defaults.​default_​overlap_for_​new_task_suites](create-pool.md#default_overlap_for_new_task_suites)) key).

Task suite overlap. ||
|| **infinite_overlap** | **boolean \| required**

Assigning a task suite with infinite overlap. This option is used, for instance, for suites of training tasks when you want to assign them to all Tolokers:

- `true` — Use infinite overlap.
- `false` — Use the overlap that is set for the task suite or pool.||
|#

## Response {#response}

Contains a [task suite in JSON format](create-task-suite.md#body).

## See also {#see-also}

- [{#T}](../../guide/concepts/overlap-faq.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}