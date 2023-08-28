# upsert_webhook_subscriptions
`toloka.client.TolokaClient.upsert_webhook_subscriptions` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3577)

```python
upsert_webhook_subscriptions(self, subscriptions: List[WebhookSubscription])
```

Creates subscriptions.


You can create a subscription and receive notifications about events.
For example, when a pool is closed or a task's status changes, Toloka can send you a notification.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subscriptions`|**List\[[WebhookSubscription](toloka.client.webhook_subscription.WebhookSubscription.md)\]**|<p>A list of subscriptions to be created.</p>

* **Returns:**

  The result of the operation.

* **Return type:**

  [WebhookSubscriptionBatchCreateResult](toloka.client.batch_create_results.WebhookSubscriptionBatchCreateResult.md)

**Examples:**


```python
result = toloka_client.upsert_webhook_subscriptions([
    {
        'webhook_url': 'https://awesome-requester.com/toloka-webhook',
        'event_type': toloka.client.webhook_subscription.WebhookSubscription.EventType.ASSIGNMENT_CREATED,
        'pool_id': '121212'
    },
    {
        'webhook_url': 'https://awesome-requester.com/toloka-webhook',
        'event_type': toloka.client.webhook_subscription.WebhookSubscription.EventType.POOL_CLOSED,
        'pool_id': '121212'
    }
])
print(len(result.items))
```
