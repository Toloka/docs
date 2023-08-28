# UserRestrictionSortItems
`toloka.client.search_requests.UserRestrictionSortItems`

```python
UserRestrictionSortItems(self, items=None)
```

Keys for sorting Toloker restrictions in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.UserRestrictionSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`'id'` — The ID of a restriction.</li> <li>`'created'` — The restriction creation date.</li> </ul>

**Examples:**

The example shows how to find Toloker restrictions sorted by creation date in the descending order. Restrictions with equal creation dates are sorted by IDs in the ascending order.

```python
sort = toloka.client.search_requests.UserRestrictionSortItems(['-created', 'id'])
result = toloka_client.find_user_restrictions(pool_id='1086170', sort=sort, limit=10)
```
