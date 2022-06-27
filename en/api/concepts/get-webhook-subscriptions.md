# Get a subscription

Gets subscription data.

## Request {#request}

{% list tabs %}

- Production version

  ```json
  GET https://toloka.yandex.com/api/v1/webhook-subscriptions/<subscription_id>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```json
  GET https://sandbox.toloka.yandex.com/api/v1/webhook-subscriptions/<subscription_id>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | ----- 
**subscription_id** | ID of the subscription.


## Headers {#headers}

Title | Overview
----- | ----- 
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Response {#response}

Contains information about the requested subscription in JSON format.

```json
[
  {
     "webhook_url": "https://awesome-requester.com/toloka-webhook",
     "event_type": "ASSIGNMENT_CREATED",
     "pool_id": "121212",
     "id": "webhook-subscription-1",
     "created": "2020-02-03T15:00:00"
  }
]

```

#|
|| Parameter | Overview ||
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

ID of the subscription. Generated automatically. ||
|| **created** | **string**

The date and time when the subscription was created (UTC). It uses ISO 8601 format: YYYY-MM-DDThh:mm:ss[.sss]. ||
|#

