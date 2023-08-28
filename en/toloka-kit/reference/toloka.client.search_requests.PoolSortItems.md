# PoolSortItems
`toloka.client.search_requests.PoolSortItems`

```python
PoolSortItems(self, items=None)
```

Keys for sorting pools in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.PoolSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`'id'` — A pool ID.</li> <li>`'created'` — A pool creation date.</li> <li>`'last_started'` — The last opening date of a pool.</li> </ul>

**Examples:**

The example shows how to find opened pools sorted by the last opening date in the descending order. Pools with equal opening dates are sorted by IDs in the ascending order.

```python
sort = toloka.client.search_requests.PoolSortItems(['-last_started', 'id'])
result = toloka_client.find_pools(status='OPEN', sort=sort, limit=50)
```
