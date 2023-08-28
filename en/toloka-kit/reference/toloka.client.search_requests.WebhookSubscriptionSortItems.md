# WebhookSubscriptionSortItems
`toloka.client.search_requests.WebhookSubscriptionSortItems`

```python
WebhookSubscriptionSortItems(self, items=None)
```

Keys for sorting event subscriptions in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.WebhookSubscriptionSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`'id'` — A subscription ID.</li> <li>`'created'` — The creation date of a subscription.</li> </ul>

**Examples:**

The example shows how to find event subscriptions sorted by creation date in the descending order. Subscriptions with equal creation dates are sorted by IDs in the ascending order.

```python
sort = toloka.client.search_requests.WebhookSubscriptionSortItems(['-created', 'id'])
result = toloka_client.find_webhook_subscriptions(event_type='ASSIGNMENT_CREATED', pool_id='1086170', sort=sort, limit=10)
```
