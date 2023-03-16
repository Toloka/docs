# Get a list of training pools

{% include [announce](../_includes/announce.md) %}

Gets the list of created training pools (including archived pools).

## Request {#request}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/trainings
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/trainings
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
|| Parameter | Overview  ||
|| **status** | **string**

Training pool status:

- `OPEN` — Open.
- `CLOSED` — Closed.
- `LOCKED` — No possible actions.
- `ARCHIVED` — Archived. ||
|| **project_id** | **string**

ID of the project that the training pool is linked to. ||
|| **sort** | **string**

Parameters for sorting in ascending order:

- `id` — ID of the training pool.
- `created` — The date when the training pool was created, in UTC using ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`.
- `last_started` — The date when the training pool was last started, in UTC using ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`.

To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **Standard query parameters** | [limit](./standard-query-parameters.md#limit), [id_gt](./standard-query-parameters.md#id_gt), [id_gte](./standard-query-parameters.md#id_gte), [id_lt](./standard-query-parameters.md#id_lt), [id_lte](./standard-query-parameters.md#id_lte), [created_gt](./standard-query-parameters.md#created_gt), [created_gte](./standard-query-parameters.md#created_gte), [created_lt](./standard-query-parameters.md#created_lt), [created_lte](./standard-query-parameters.md#created_lte), [last_started_gt](./standard-query-parameters.md#last_started_gt), [last_started_gte](./standard-query-parameters.md#last_started_gte), [last_started_gte](./standard-query-parameters.md#last_started_gte), [last_started_lt](./standard-query-parameters.md#last_started_lt), [last_started_lte](./standard-query-parameters.md#last_started_lte). ||
|#

## Query example {#request-example}

You can set up the display of the list of pools in parts (for example, 10 pools at a time):

1. Show the first 10 pools, starting with the pool with the lowest ID.
1. Show the remaining pools (10 at a time) in ascending order.

**Show the first 10 pools**

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/trainings?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/trainings?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

**Show the remaining tasks sorted by ascending ID**

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/trainings?sort=id&limit=10&id_gt=<id of the last training from the previous response>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/trainings?sort=id&limit=10&id_gt=<id of the last training from the previous response>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Response {#response}

```json
{"items" : [{parameters_of_training_pool_1}, {parameters_of_training_pool_2}, ... {parameters_of_training_pool__n_}], "has_more": false}
```

#|
|| Property | Description ||
|| **items[]** | **array of objects**

Contains a list of training pools and their properties. ||
|| **has_more** | {% include [has-more](../_includes/has-more.md) %} ||
|#

{% include [contact-support](../../guide/_includes/contact-support.md) %}