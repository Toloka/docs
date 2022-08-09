# Create a subscription

{% include [announce](../_includes/announce.md) %}

Creates one or more subscriptions.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    PUT https://toloka.dev/api/v1/webhook-subscriptions
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    PUT https://sandbox.toloka.dev/api/v1/webhook-subscriptions
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

```json
[
  {
    "webhook_url": "https://awesome-requester.com/toloka-webhook",
    "event_type": "ASSIGNMENT_CREATED",
    "pool_id": "121212"
  },
  {
    "webhook_url": "https://awesome-requester.com/toloka-webhook",
    "event_type": "POOL_CLOSED",
    "pool_id": "121212",
    "secret_key": "12345"
  }
]
```

#|
|| Parameter | Overview ||
|| **webhook_url** | **string \| required**

The URL that notifications will be sent to. ||
|| **event_type** {#event} | **string \| required**

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
|| **pool_id** | **string \| required**

ID of the pool that the subscription was created for. ||
|| **secret_key** | **string \| optional**
A secret key with which you can check whether incoming requests were sent through the Toloka API. For more information, see [Event authentication](authentication.md). ||
|#

## Response {#response}

Contains information about created subscriptions in JSON format. Each subscription is assigned a unique identifier (`id`) and creation date (`created`).

{% list tabs %}

- When creating a single subscription

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

- When creating multiple subscriptions

    ```json
    {
      "items": [
        "0": {
          "webhook_url": "https://awesome-requester.com/toloka-webhook",
          "event_type": "ASSIGNMENT_CREATED",
          "pool_id": "121212",
          "id": "webhook-subscription-1",
          "created": "2020-02-03T15:00:00"
        },
        "1": {
          "webhook_url": "https://awesome-requester.com/toloka-webhook",
          "event_type": "POOL_CLOSED",
          "pool_id": "121212",
          "id": "webhook-subscription-2",
          "created": "2020-02-03T15:00:00"
        }
      ],
      "validation_errors": {}
    }
    ```

{% endlist %}

#|
|| Parameter | Overview ||
|| **items[]** | **array of objects**

An array of objects with information about the subscriptions created. ||
|| **\<n\>** | **object**

Sequential number of the subscription in the creation request (starting from 0). ||
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

The date and time when the subscription was created (UTC). It uses ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **validation_errors** | **object**

Object with validation errors. ||
|#