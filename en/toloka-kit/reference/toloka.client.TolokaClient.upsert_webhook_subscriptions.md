# upsert_webhook_subscriptions
`toloka.client.TolokaClient.upsert_webhook_subscriptions` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/__init__.py#L3488)

```python
upsert_webhook_subscriptions(self, subscriptions: List[WebhookSubscription])
```

Creates (upsert) webhook subscriptions.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`subscriptions`|**List\[[WebhookSubscription](toloka.client.webhook_subscription.WebhookSubscription.md)\]**|<p>A list of webhook subscriptions to be created.</p>

* **Returns:**

  The result of the operation.

* **Return type:**

  [WebhookSubscriptionBatchCreateResult](toloka.client.batch_create_results.WebhookSubscriptionBatchCreateResult.md)

**Examples:**

How to create several subscriptions.

```python
created_result = toloka_client.upsert_webhook_subscriptions([
    {
        'webhook_url': 'https://awesome-requester.com/toloka-webhook',
        'event_type': toloka.webhook_subscription.WebhookSubscription.EventType.ASSIGNMENT_CREATED,
        'pool_id': '121212'
    },
    {
        'webhook_url': 'https://awesome-requester.com/toloka-webhook',
        'event_type': toloka.webhook_subscription.WebhookSubscription.EventType.POOL_CLOSED,
        'pool_id': '121212',
    }
])
print(len(created_result.items))
```
