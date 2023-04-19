# Edit a training pool

{% include [announce](../_includes/announce.md) %}

Makes changes to a training pool.

Learn about editing a main pool in the [Edit pool](edit-pool.md) section.

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#put-/trainings/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

    ```bash
    PUT https://toloka.dev/api/v1/trainings/<training_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<training parameters, including updated ones>}
    ```

- Sandbox

    ```bash
    PUT https://sandbox.toloka.dev/api/v1/trainings/<training_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<training parameters, including updated ones>}
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
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

In the request body, specify **all** the pool [parameters](create-training.md#training-param), including those that are updated.

## Response {#response}

Contains information about a modified training pool (see the description in the [Create a training pool](create-training.md#response) section).

{% include [contact-support](../../guide/_includes/contact-support.md) %}