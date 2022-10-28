# WebhookSubscriptionSearchResult
`toloka.client.search_results.WebhookSubscriptionSearchResult`

```python
WebhookSubscriptionSearchResult(
    self,
    *,
    items: Optional[List[WebhookSubscription]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching webhook subscriptions.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[WebhookSubscription](toloka.client.webhook_subscription.WebhookSubscription.md)\]\]**|<p>A list with found subscriptions.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching subscriptions.</p> <ul> <li>`True` — There are more matching subscriptions, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching subscriptions.</li> </ul>
