# UserBonusSortItems
`toloka.client.search_requests.UserBonusSortItems`

```python
UserBonusSortItems(self, items=None)
```

Keys for sorting bonuses in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.UserBonusSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`'id'` — The ID of a bonus.</li> <li>`'created'` — The date of granting a bonus.</li> </ul>

**Examples:**

The example shows how to find bonuses sorted by granting date in the descending order. Bonuses with equal granting dates are sorted by IDs in the ascending order.

```python
sort = toloka.client.search_requests.UserBonusSortItems(['-created', 'id'])
result = toloka_client.find_user_bonuses(user_id='fac97860c7929add8048ed2ef63b66fd', sort=sort, limit=10)
```
