# EventType
`toloka.client.webhook_subscription.WebhookSubscription.EventType` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/webhook_subscription.py#L25)

An event type.

## Attributes Description

| Name | Value | Description |
| :------| :-----------| :----------|
`POOL_CLOSED`|'POOL_CLOSED'|<p>A pool is closed.</p>
`DYNAMIC_OVERLAP_COMPLETED`|'DYNAMIC_OVERLAP_COMPLETED'|<p>An aggregated result is ready for a task with a dynamic overlap.</p>
`ASSIGNMENT_CREATED`|'ASSIGNMENT_CREATED'|<p>A task is created.</p>
`ASSIGNMENT_SUBMITTED`|'ASSIGNMENT_SUBMITTED'|<p>A task is completed and waiting for acceptance by a requester.</p>
`ASSIGNMENT_SKIPPED`|'ASSIGNMENT_SKIPPED'|<p>A task was taken by a Toloker who skipped it and didn't return to it.</p>
`ASSIGNMENT_EXPIRED`|'ASSIGNMENT_EXPIRED'|<p>A task was taken by a Toloker who didn't complete it within the time limit or rejected it before it expired.</p>
`ASSIGNMENT_APPROVED`|'ASSIGNMENT_APPROVED'|<p>A task was completed by a Toloker and approved by a requester.</p>
`ASSIGNMENT_REJECTED`|'ASSIGNMENT_REJECTED'|<p>A task was completed by a Toloker but rejected by a requester.</p>
