# TaskSearchResult
`toloka.client.search_results.TaskSearchResult`

```python
TaskSearchResult(
    self,
    *,
    items: Optional[List[Task]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching tasks.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[Task](toloka.client.task.Task.md)\]\]**|<p>A list with found tasks.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching tasks.</p> <ul> <li>`True` — There are more matching tasks, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching tasks.</li> </ul>
