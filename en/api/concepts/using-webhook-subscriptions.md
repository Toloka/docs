# Notification format

When an event that a [subscription is created](https://toloka.ai/docs/api/api-reference/#put-/webhook-subscriptions) for occurs, a notification is sent to the URL specified in the subscription. It will contain all data about the object as of the event time.

Notifications are sent in JSON format.

```json
{
  "events":[
    {Event data 1},
    {Event data 2},
    {Event data N}
  ]
}
```

Data included in a notification depends on the [event type](https://toloka.ai/docs/api/api-reference/#put-/webhook-subscriptions#event).

If the **secret_key** parameter is specified when creating a subscription, an additional header — **Toloka-Signature** — appears in the event notification headers. It confirms that the requests were sent via the Toloka API. For more information, see [Event authentication](authentication.md).

## Example of the POOL_CLOSED notification body {#pool-closed}

```json
{
  "uuid": "uuid-1",
  "event_time": "2020-02-14T12:22:58",
  "project_id": "project-1",
  "pool_id": "pool-1",
  "close_reason": "MANUAL",
  "webhook_subscription_id": "subscription-1",
  "type": "POOL_CLOSED"
}
```

#|
|| Parameter | Overview ||
|| `uuid` | _string_

Unique event ID. ||
|| `event_time` | _string_

Time when the event occurs. ||
|| `project_id` | _string_

ID of the project that the pool was created for. ||
|| `pool_id` | _string_

ID of the pool that the subscription was created for. ||
|| `close_reason` | _string_

Reason for closing the pool. ||
|| `webhook_subscription_id` | _string_

ID of the subscription. ||
|| `type` | _string_

Event type.

Possible value: `POOL_CLOSED` — The pool is closed. ||
|#

## Example of the ASSIGNMENT_CREATED notification body {#assignment}

```json
{
  "uuid": "uuid-1",
  "event_time": "2020-02-14T12:23:05",
  "project_id": "project-1",
  "pool_id": "pool-1",
  "task_suite_id": "task suite-1",
  "assignment_id": "assignment-1",
  "webhook_subscription_id": "subscription-1",
  "type": "ASSIGNMENT_CREATED"
}
```

#|
|| Parameter | Overview ||
|| `uuid` | _string_

Unique event ID. ||
|| `event_time` | _string_

Time when the event occurs. ||
|| `project_id` | _string_

ID of the project that the pool was created for. ||
|| `pool_id` | _string_

ID of the pool that the subscription was created for. ||
|| `task_suite_id` | _string_

ID of a task suite. ||
|| `assignment_id` | _string_

ID of the assignment to a Toloker. ||
|| `webhook_subscription_id` | _string_

ID of the subscription. ||
|| `type` | _string_

Event type.

Acceptable values:

- `ASSIGNMENT_CREATED` — A task is created.
- `ASSIGNMENT_SUBMITTED` — A task is completed and waiting for acceptance by the requester.
- `ASSIGNMENT_SKIPPED` — A task was taken by the Toloker who then skipped it and won't return to it.
- `ASSIGNMENT_EXPIRED` — A task was taken by the Toloker who failed to complete it within the time allowed or rejected it before it expired.
- `ASSIGNMENT_APPROVED` — A task was completed by the Toloker and approved by the requester.
- `ASSIGNMENT_REJECTED` — A task was completed by the Toloker but rejected by the requester.
||
|#

## Example of the DYNAMIC_OVERLAP_COMPLETED notification body {#dynamic-overlap-completed}

```json
{
  "uuid": "uuid-1",
  "event_time": "2020-02-14T12:23:05",
  "project_id": "project-1",
  "pool_id": "pool-2",
  "task_id": "task-1",
  "confidence": 0.155,
  "webhook_subscription_id": "subscription-1",
  "type": "DYNAMIC_OVERLAP_COMPLETED",
  "assignment_ids": ["assignment-1", "assignment-2"],
  "output_values": {
    "field_one": "value-1"
  }
}
```

#|
|| Parameter | Overview ||
|| `uuid` | _string_

Unique event ID. ||
|| `event_time` | _string_

Time when the event occurs. ||
|| `project_id` | _string_

ID of the project that the pool was created for. ||
|| `pool_id` | _string_

ID of the pool that the subscription was created for. ||
|| `task_id` | _string_

Task ID. ||
|| `confidence` | _integer_

Confidence in the aggregate response. ||
|| `webhook_subscription_id` | _string_

ID of the subscription. ||
|| `type` | _string_

Event type.

Possible value: `DYNAMIC_OVERLAP_COMPLETED` — An aggregated score appeared after dynamic overlap. ||
|| `assignment_ids[]` | _array of strings_

IDs of assignments to Tolokers. ||
|| `output_values[]` | _array of objects_

Output data fields that contain the task text (`field_one`) and response. ||
|#

{% include [contact-support](../../guide/_includes/contact-support.md) %}