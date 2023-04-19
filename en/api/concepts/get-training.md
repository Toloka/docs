# Get training properties

{% include [announce](../_includes/announce.md) %}

Gets the properties of a training pool.

You can get the training pool ID from the [list of training pools](get-training-list.md).

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#get-/trainings/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/trainings/<training_id>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/trainings/<training_id>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**training_id** | Pool ID.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Response {#response}

Contains information about a training pool (see the description in the [Create a training pool](create-training.md#response) section).

{% include [contact-support](../../guide/_includes/contact-support.md) %}