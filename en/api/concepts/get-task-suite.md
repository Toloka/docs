# Get a task suite

{% include [announce](../_includes/announce.md) %}

Gets a task suite.

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#get-/task-suites/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/task-suites/<task_suite_id>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/task-suites/<task_suite_id>
  Authorization: OAuth <OAuth token>
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

## Response {#response}

Contains a [task suite in JSON format](create-task-suite.md#body).

{% include [contact-support](../../guide/_includes/contact-support.md) %}