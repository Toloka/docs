# Change pool priority

Changes the priority of a pool.

If you have multiple pools and want Tolokers to be offered one pool before another, change the pool priority. You don't need to stop the pool for that, it must have the "open" or "closed" status.

Priority is a number on a scale from 0 to 100. The larger the number, the faster the pool will be labeled compared to your other pools.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    PATCH https://toloka.yandex.com/api/v1/pools/<pool_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    PATCH https://sandbox.toloka.yandex.com/api/v1/pools/<pool_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
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

```json
{
  "priority": <from 0 to 100>
}
```

#|
|| Parameter | Overview ||
|| **Priority** | **integer**

The priority of the pool in relation to other pools in the project with the same task price and set of filters. Users are assigned tasks with a higher priority first.

Possible values: from `-100` to `100`.

By default the value is `0` . ||
|#

## Response {#response}

{% note info %}

If the pool is archived, an empty response with status 409 is returned.

{% endnote %}

Contains updated information about the pool (see the description in the [Create a pool](create-pool.md#response) section).