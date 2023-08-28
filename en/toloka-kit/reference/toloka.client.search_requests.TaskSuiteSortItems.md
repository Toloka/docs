# TaskSuiteSortItems
`toloka.client.search_requests.TaskSuiteSortItems`

```python
TaskSuiteSortItems(self, items=None)
```

Keys for sorting task suites in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.TaskSuiteSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`'id'` — The ID of a task suite.</li> <li>`'created'` — The creation date of a task suite.</li> </ul>

**Examples:**

The example shows how to find task suites sorted by the creation date in the descending order. Task suites with equal creation dates are sorted by IDs in the descending order.

```python
sort = toloka.client.search_requests.TaskSuiteSortItems(['-created', '-id'])
result = toloka_client.find_task_suites(pool_id='1086170', sort=sort, limit=10)
```
