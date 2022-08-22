# Edit a pool

{% include [announce](../_includes/announce.md) %}

Makes changes to a pool.

The pool can't be edited if it's open. [Close the pool](close-pool-for-update.md) before editing.

{% note info %}

Learn about editing a training pool in the section [Edit a training pool](edit-training.md).

{% endnote %}

## Request {#request}

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