# delete_webhook_subscription
`toloka.client.TolokaClient.delete_webhook_subscription` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3692)

```python
delete_webhook_subscription(self, webhook_subscription_id: str)
```

Deletes a subscription.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`webhook_subscription_id`|**str**|<p>The ID of the subscription.</p>

**Examples:**


```python
subscription = toloka_client.delete_webhook_subscription('62f29db0a451956b21e13ff2')
```
