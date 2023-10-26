# WebhookSubscription
`toloka.client.webhook_subscription.WebhookSubscription` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/webhook_subscription.py#L11)

```python
WebhookSubscription(
    self,
    *,
    webhook_url: Optional[str] = None,
    event_type: Union[EventType, str, None] = None,
    pool_id: Optional[str] = None,
    secret_key: Optional[str] = None,
    id: Optional[str] = None,
    created: Optional[datetime] = None
)
```

A subscription to an event in Toloka.


For examples, you can receive notifications when a pool is closed or a task's status changes.
Learn more about [notifications](https://toloka.ai/docs/api/using-webhook-subscriptions/).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the subscription. Read-only field.</p>
`webhook_url`|**Optional\[str\]**|<p>The URL to which notifications are sent.</p>
`event_type`|**Optional\[[EventType](toloka.client.webhook_subscription.WebhookSubscription.EventType.md)\]**|<p>The event type.</p>
`pool_id`|**Optional\[str\]**|<p>The ID of the pool that the subscription was created for.</p>
`created`|**Optional\[datetime\]**|<p>The UTC date and time when the subscription was created. Read-only field.</p>
