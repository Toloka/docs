# Get properties of a pool

{% include [announce](../_includes/announce.md) %}

Gets the properties of a pool.

You can get the pool ID from the [list of pools](get-pool-list.md).

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#get-/pools/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/pools/<pool_id>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/pools/<pool_id>
  Authorization: OAuth <OAuth token>
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

## Response {#response}

Contains pool parameters (see the description in the [Create a pool](create-pool.md#response) section).

{% include [contact-support](../../guide/_includes/contact-support.md) %}