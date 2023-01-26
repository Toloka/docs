# get_webhook_subscriptions
`toloka.async_client.client.AsyncTolokaClient.get_webhook_subscriptions` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/__init__.py#L0)

Finds all webhook subscriptions that match certain criteria.


`get_webhook_subscriptions` returns a generator. You can iterate over all found webhook subscriptions using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort webhook subscriptions use the [find_webhook_subscriptions](toloka.client.TolokaClient.find_webhook_subscriptions.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`event_type`|**Optional\[[WebhookSubscription.EventType](toloka.client.webhook_subscription.WebhookSubscription.EventType.md)\]**|<p>Event type. Refer to the [EventType](toloka.client.webhook_subscription.WebhookSubscription.EventType.md) page for more information on the available `event_type` values.</p>
`pool_id`|**Optional\[str\]**|<p>The ID of a subscribed pool.</p>
`id_lt`|**Optional\[str\]**|<p>Subscriptions with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Subscriptions with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Subscriptions with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Subscriptions with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Subscriptions created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Subscriptions created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Subscriptions created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Subscriptions created after or on the specified date.</p>
`batch_size`|**Optional\[int\]**|<p>Returned webhook subscriptions limit for each request. The maximum allowed batch_size is 300.</p>

* **Yields:**

  The next matching webhook subscription.

* **Yield type:**

  [AsyncGenAdapter](toloka.util.async_utils.AsyncGenAdapter.md)\[[WebhookSubscription](toloka.client.webhook_subscription.WebhookSubscription.md), None\]
