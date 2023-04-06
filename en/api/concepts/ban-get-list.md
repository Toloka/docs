# Get a list of bans

{% include [announce](../_includes/announce.md) %}

Gets the list of Toloker bans.

## Request {#request}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/user-restrictions
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/user-restrictions
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Query parameters {#query-params}

{% include [query-params](../_includes/query-params.md) %}

#|
|| Parameter | Overview ||
|| **scope** | **string**

The scope of the ban:

- `ALL_PROJECTS` — All the requester's projects.
- `PROJECT` — A single project (specify the `project_id`).
- `POOL` — A pool (specify the `pool_id`).
- `SYSTEM` — Users that performed the requester's tasks but were [banned on the platform](../../guide/concepts/ban.md#ban__ban-platform). ||
|| **user_id** | **string**

Toloker ID. ||
|| **project_id** | **string \| required if**

Required if `scope=PROJECT`.

The ID of the project that is blocked. ||
|| **pool_id** | **string \| required if**

Required if `scope=POOL`.

The ID of the pool that is blocked. ||

|| **sort** | **string**

Parameters to sort by:

- `id` — The ID.
- `created` — The creation date in UTC using ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`.

To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **Standard query parameters** | [limit](standard-query-parameters.md#limit), [id_gt](standard-query-parameters.md#id_gt), [id_gte](standard-query-parameters.md#id_gte), [id_lt](standard-query-parameters.md#id_lt), [id_lte](standard-query-parameters.md#id_lte), [created_gt](standard-query-parameters.md#created_gt), [created_gte](standard-query-parameters.md#created_gte), [created_lt](standard-query-parameters.md#created_lt), [created_lte](standard-query-parameters.md#created_lte). ||
|#

## Query example {#request-example}

To get the list of bans in parts (for example, 10 bans at a time), use a combination of parameters in requests:

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/user-restrictions?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

  ```bash
  GET https://toloka.dev/api/v1/user-restrictions?sort=id&limit=10&id_gt=<id last ban from the answer to the previous query>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/user-restrictions?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

  ```bash
  GET https://sandbox.toloka.dev/api/v1/user-restrictions?sort=id&limit=10&id_gt=<id last ban from the answer to the previous query>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Response {#response}

```json
{"items" : [{ban parameters 1}, {ban parameters 2}, ... {ban parameters n}], "has_more": true}
```

#|
|| Property | Description ||
|| **items[]** | **array of objects**

Contains a list of bans. ||
|| **has_more** | {% include [has-more](../_includes/has-more.md) %} ||
|#

{% include [contact-support](../../guide/_includes/contact-support.md) %}