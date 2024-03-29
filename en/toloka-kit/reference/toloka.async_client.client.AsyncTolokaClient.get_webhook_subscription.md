# get_webhook_subscription
`toloka.async_client.client.AsyncTolokaClient.get_webhook_subscription` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/async_client/client.py#L0)

```python
async get_webhook_subscription(self, webhook_subscription_id: str)
```

Gets the properties of a subscription from Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`webhook_subscription_id`|**str**|<p>The ID of the subscription.</p>

* **Returns:**

  The subscription.

* **Return type:**

  [WebhookSubscription](toloka.client.webhook_subscription.WebhookSubscription.md)

**Examples:**


```python
subscription = toloka_client.get_webhook_subscription('62f29db0a451956b21e13ff2')
print(subscription.event_type, subscription.webhook_url)
```
