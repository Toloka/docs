# TrainingSortItems
`toloka.client.search_requests.TrainingSortItems`

```python
TrainingSortItems(self, items=None)
```

Keys for sorting training pools in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.TrainingSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`'id'` — Training pool ID.</li> <li>`'created'` — Training pool creation date.</li> <li>`'last_started'` — The last opening date of a training pool.</li> </ul>

**Examples:**

The example shows how to find opened training pools sorted by the last opening date in the descending order. Pools with equal opening dates are sorted by IDs in the ascending order.

```python
sort = toloka.client.search_requests.TrainingSortItems(['-last_started', 'id'])
result = toloka_client.find_trainings(status='OPEN', sort=sort, limit=50)
```
