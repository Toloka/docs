# WebhookSubscriptionBatchCreateResult
`toloka.client.batch_create_results.WebhookSubscriptionBatchCreateResult`

```python
WebhookSubscriptionBatchCreateResult(
    self,
    *,
    items: Optional[Dict[str, WebhookSubscription]] = None,
    validation_errors: Optional[Dict[str, Dict[str, FieldValidationError]]] = None
)
```

The result of creating webhook subscriptions.


`WebhookSubscriptionBatchCreateResult` is returned by the [upsert_webhook_subscriptions](toloka.client.TolokaClient.upsert_webhook_subscriptions.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Dict\[str, [WebhookSubscription](toloka.client.webhook_subscription.WebhookSubscription.md)\]\]**|<p>A dictionary with created subscriptions. The indexes of a `upsert_webhook_subscriptions` input list are used as keys in the dictionary.</p>
`validation_errors`|**Optional\[Dict\[str, Dict\[str, [FieldValidationError](toloka.client.batch_create_results.FieldValidationError.md)\]\]\]**|<p>A dictionary with validation errors.</p>

**Examples:**


```python
result = toloka_client.upsert_webhook_subscriptions([
    {
        'webhook_url': 'https://awesome-requester.com/toloka-webhook',
        'event_type': toloka.client.webhook_subscription.WebhookSubscription.EventType.ASSIGNMENT_CREATED,
        'pool_id': '1240045'
    }
])
print(result.items['0'].created)
```
