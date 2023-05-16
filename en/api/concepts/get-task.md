# Get a task

{% include [announce](../_includes/announce.md) %}

Gets task data.

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#get-/tasks/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/tasks/<task_id>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/tasks/<task_id>
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

{% include [contact-support](../../guide/_includes/contact-support.md) %}