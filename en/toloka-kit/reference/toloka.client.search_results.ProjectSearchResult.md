# ProjectSearchResult
`toloka.client.search_results.ProjectSearchResult`

```python
ProjectSearchResult(
    self,
    *,
    items: Optional[List[Project]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching projects.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[Project](toloka.client.project.Project.md)\]\]**|<p>A list with found projects.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching projects.</p> <ul> <li>`True` — There are more matching projects, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching projects.</li> </ul>
