# Get properties of a pool

Gets the properties of a pool.

You can get the pool ID from the [list of pools](get-pool-list.md).

## Request {#request}

{% list tabs %}

- Production version

	```json
	GET https://toloka.yandex.com/api/v1/pools/<pool_id>
	Authorization: OAuth <OAuth token>
	```

- Sandbox

	```json
	GET https://sandbox.toloka.yandex.com/api/v1/pools/<pool_id>
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

