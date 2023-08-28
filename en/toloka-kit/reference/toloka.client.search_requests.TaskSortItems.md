# TaskSortItems
`toloka.client.search_requests.TaskSortItems`

```python
TaskSortItems(self, items=None)
```

Keys for sorting tasks in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.TaskSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`&#x27;id&#x27;` — The ID of a task.</li> <li>`&#x27;created&#x27;` — The creation date of a task.</li> </ul>

**Examples:**

The example shows how to find tasks sorted by creation dates in descending order. Tasks with equal creation dates are sorted by IDs in descending order.

```python
sort = toloka.client.search_requests.TaskSortItems(['-created', '-id'])
result = toloka_client.find_tasks(pool_id='1086170', sort=sort, limit=10)
```
