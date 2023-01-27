# get_webhook_subscription
`toloka.async_client.client.AsyncTolokaClient.get_webhook_subscription` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/async_client/client.py#L0)

```python
async get_webhook_subscription(self, webhook_subscription_id: str)
```

Get one specific webhook-subscription

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`webhook_subscription_id`|**str**|<p>ID of the subscription.</p>

* **Returns:**

  The subscription.

* **Return type:**

  [WebhookSubscription](toloka.client.webhook_subscription.WebhookSubscription.md)
