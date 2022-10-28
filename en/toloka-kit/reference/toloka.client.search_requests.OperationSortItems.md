# OperationSortItems
`toloka.client.search_requests.OperationSortItems`

```python
OperationSortItems(self, items=None)
```

Keys for sorting operations in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.OperationSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`&#x27;id&#x27;` — Operation ID.</li> <li>`&#x27;submitted&#x27;` — The date and time when the request was sent.</li> <li>`&#x27;finished&#x27;` — The date and time when the operation was finished.</li> </ul>

**Examples:**

The example shows how to find operations sorted by finish date in descending order. Operations with equal finish dates are sorted by IDs in ascending order.

```python
sort = toloka.client.search_requests.OperationsSearchRequest(['-finished', 'id'])
result = toloka_client.find_operations(type='POOL_OPEN', status='SUCCESS', sort=sort, limit=10)
```
