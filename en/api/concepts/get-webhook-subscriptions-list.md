# Get a list of subscriptions

Gets data for multiple active subscriptions.

## Request {#request}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.yandex.com/api/v1/webhook-subscriptions
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/webhook-subscriptions
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
|| **event_type** | **string**

Event type.

Acceptable values:

- `POOL_CLOSED` — The pool is closed.
- `DYNAMIC_OVERLAP_COMPLETED` — An aggregated result appeared after dynamic overlap.
- `ASSIGNMENT_CREATED` — A task is created.
- `ASSIGNMENT_SUBMITTED` — A task is completed and waiting for acceptance by the requester.
- `ASSIGNMENT_SKIPPED` — A task was taken by the Toloker who then skipped it and won't return to it.
- `ASSIGNMENT_EXPIRED` — A task was taken by the Toloker who failed to complete it within the time allowed or rejected it before it expired.
- `ASSIGNMENT_APPROVED` — A task was completed by the Toloker and approved by the requester.
- `ASSIGNMENT_REJECTED` — A task was completed by the Toloker but rejected by the requester. ||
|| **pool_id** | **string**

ID of the pool that subscription information is requested for. ||
|| **sort** | **string**

Parameters to sort by:

- `id` — Subscription ID.

- `created` — The subscription creation date in UTC using ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss].


To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **Standard query parameters** |
[limit](./standard-query-parameters.md#limit), [id_gt](./standard-query-parameters.md#id_gt), [id_gte](./standard-query-parameters.md#id_gte), [id_lt](./standard-query-parameters.md#id_lt), [id_lte](./standard-query-parameters.md#id_lte), [created_gt](./standard-query-parameters.md#created_gt), [created_gte](./standard-query-parameters.md#created_gte), [created_lt](./standard-query-parameters.md#created_lt), [created_lte](./standard-query-parameters.md#created_lte). ||
|#

## Query example {#request-example}

You can set up the display of the list of subscriptions in parts (for example, 10 subscriptions at a time):
1. Show the first 10 subscriptions, starting with the one with the lowest ID.
1. Show the remaining subscriptions (10 at a time) in ascending order.

**Show the first 10 subscriptions**

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.yandex.com/api/v1/webhook-subscriptions?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/webhook-subscriptions?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

**Show the remaining tasks sorted by ascending ID**

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.yandex.com/api/v1/webhook-subscriptions?sort=id&limit=10&id_gt=<ID of the last subsciption from the previous response>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/webhook-subscriptions?sort=id&limit=10&id_gt=<ID of the last subsciption from the previous response>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Response {#response}

Contains a list of subscriptions with information about each of them in JSON format.

```json
{
  items: [
    {
       "webhook_url": "https://awesome-requester.com/toloka-webhook",
       "event_type": "ASSIGNMENT_CREATED",
       "pool_id": "121212",
       "id": "webhook-subscription-1",
       "created": "2020-02-03T15:00:00"
    },
    {
       "webhook_url": "https://awesome-requester.com/toloka-webhook",
       "event_type": "POOL_CLOSED",
       "pool_id": "121212",
       "id": "webhook-subscription-2",
       "created": "2020-02-03T15:00:00"
    }
  ],
  has_more: false
}
```

#|
|| Parameter | Overview ||
|| **items[]** | **array of objects**

An array of objects with information about the requested subscriptions. ||
|| **webhook_url** | **string**

The URL that notifications will be sent to. ||
|| **event_type** | **string**

Event type.

Acceptable values:

- `POOL_CLOSED` — The pool is closed.
- `DYNAMIC_OVERLAP_COMPLETED` — An aggregated result appeared after dynamic overlap.
- `ASSIGNMENT_CREATED` — A task is created.
- `ASSIGNMENT_SUBMITTED` — A task is completed and waiting for acceptance by the requester.
- `ASSIGNMENT_SKIPPED` — A task was taken by the Toloker who then skipped it and won't return to it.
- `ASSIGNMENT_EXPIRED` — A task was taken by the Toloker who failed to complete it within the time allowed or rejected it before it expired.
- `ASSIGNMENT_APPROVED` — A task was completed by the Toloker and approved by the requester.
- `ASSIGNMENT_REJECTED` — A task was completed by the Toloker but rejected by the requester. ||
|| **pool_id** | **string**

ID of the pool that the subscription was created for. ||
|| **id** | **string**

ID of the subscription. ||
|| **created** | **string**

The date and time when the subscription was created (UTC). It uses ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|| **has_more** | **boolean**

Shows whether the list is complete.

Acceptable values:

- `true` — Not all elements are included in the output due to restrictions in the `limit` parameter.

- `false` — The output lists all the items. ||
|#
