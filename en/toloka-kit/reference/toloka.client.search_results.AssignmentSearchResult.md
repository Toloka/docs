# AssignmentSearchResult
`toloka.client.search_results.AssignmentSearchResult`

```python
AssignmentSearchResult(
    self,
    *,
    items: Optional[List[Assignment]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching assignments.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[Assignment](toloka.client.assignment.Assignment.md)\]\]**|<p>A list with found assignments.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching assignments.</p> <ul> <li>`True` — There are more matching assignments, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching assignments.</li> </ul>
