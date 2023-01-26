# find_webhook_subscriptions
`toloka.client.TolokaClient.find_webhook_subscriptions` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/__init__.py#L3424)

Finds webhook subscriptions that match certain criteria.


The number of returned webhook subscriptions is limited. To find remaining webhook subscriptions call `find_webhook_subscriptions` with updated search criteria.

To iterate over all matching webhook subscriptions you may use the [get_webhook_subscriptions](toloka.client.TolokaClient.get_webhook_subscriptions.md) method.

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
`sort`|**Union\[List\[str\], [WebhookSubscriptionSortItems](toloka.client.search_requests.WebhookSubscriptionSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned webhook subscriptions limit. The maximum allowed limit is 300.</p>

* **Returns:**

  Found webhook subscriptions and a flag showing whether there are more matching webhook subscriptions exceeding the limit.

* **Return type:**

  [WebhookSubscriptionSearchResult](toloka.client.search_results.WebhookSubscriptionSearchResult.md)
