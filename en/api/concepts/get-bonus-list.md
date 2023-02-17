# Get a list of rewards issued

{% include [announce](../_includes/announce.md) %}

Gets a list of rewards issued.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/user-bonuses
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-bonuses
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **user_id** | **string**

Toloker ID. ||
|| **assignment_id** | **string**

ID of the Toloker's response to the task a reward is issued for. ||
|| **private_comment** | **string**

Comments that are only visible to the requester. ||
|| **sort** | **string**

Parameters to sort by:

- `id` — Reward ID.
- `created` — The date when the reward was awarded, in UTC using ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`.

To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **Standard query parameters** | [limit](./standard-query-parameters.md#limit), [id_gt](./standard-query-parameters.md#id_gt), [id_gte](./standard-query-parameters.md#id_gte), [id_lt](./standard-query-parameters.md#id_lt), [id_lte](./standard-query-parameters.md#id_lte), [created_gt](./standard-query-parameters.md#created_gt), [created_gte](./standard-query-parameters.md#created_gte), [created_lt](./standard-query-parameters.md#created_lt), [created_lte](./standard-query-parameters.md#created_lte). ||
|#

## Query example {#request-example}

You can set up the display of the list of rewards in parts (for example, 10 rewards at a time):

1. Show the first 10 rewards, starting with the one with the lowest ID.
1. Show the remaining rewards (10 at a time) in ascending order.

**Show the first 10 rewards**

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/user-bonuses?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-bonuses?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

**Show the remaining tasks sorted by ascending ID**

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/user-bonuses?sort=id&limit=10&id_gt=<ID of the last bonus from the previous response>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-bonuses?sort=id&limit=10&id_gt=<ID of the last bonus from the previous response>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Response {#response}

[Information about rewards](get-one-bonus.md) in the `items` array:

```json
{"items" : [{bonus #1}, {bonus #2}, ... {bonus #n}], "has_more": true}
```

{% include [contact-support](../../guide/_includes/contact-support.md) %}