# TaskSuiteSortItems
`toloka.client.search_requests.TaskSuiteSortItems`

```python
TaskSuiteSortItems(self, items=None)
```

Keys for sorting task suites in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.TaskSuiteSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`&#x27;id&#x27;` — The ID of a task suite.</li> <li>`&#x27;created&#x27;` — The creation date of a task suite.</li> </ul>

**Examples:**

The example shows how to find task suites sorted by the creation date in descending order. Task suites with equal creation dates are sorted by IDs in ascending order.

```python
sort = toloka.client.search_requests.TaskSuiteSortItems(['-created', 'id'])
result = toloka_client.find_task_suites(pool_id=my_pool_id, sort=sort, limit=10)
```
