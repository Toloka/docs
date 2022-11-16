# TaskSuiteSearchResult
`toloka.client.search_results.TaskSuiteSearchResult`

```python
TaskSuiteSearchResult(
    self,
    *,
    items: Optional[List[TaskSuite]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching task suites.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[TaskSuite](toloka.client.task_suite.TaskSuite.md)\]\]**|<p>A list with found task suites.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching task suites.</p> <ul> <li>`True` — There are more matching task suites, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching task suites.</li> </ul>
