# Edit a pool

{% include [announce](../_includes/announce.md) %}

Makes changes to a pool.

The pool can't be edited if it's open. [Close the pool](close-pool-for-update.md) before editing.

{% note alert "Restriction" %}

You can send a maximum of 10 requests per hour to change the pool overlap parameters values. Refer to the [Rate limiting](rate-limiting.md) section for the complete list of the request limitations in Toloka API.

{% endnote %}

Learn about editing a training pool in the [Edit a training pool](edit-training.md) section.

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#put-/pools/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

    ```bash
    PUT https://toloka.dev/api/v1/pools/<pool_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<pool parameters, including updated ones>}
    ```

- Sandbox

    ```bash
    PUT https://sandbox.toloka.dev/api/v1/pools/<pool_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<pool parameters, including updated ones>}
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**pool_id** | Pool ID.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

In the request body, specify **all** the pool [parameters](create-pool.md#pool-param), including those that are updated.

## Response {#response}

Contains updated information about the pool (see the description in the [Create a pool](create-pool.md#response) section).

## See also {#see-also}

- [{#T}](../../guide/concepts/pool-edit.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}