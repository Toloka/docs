# AppProjectSearchResult
`toloka.client.search_results.AppProjectSearchResult`

```python
AppProjectSearchResult(
    self,
    *,
    content: Optional[List[AppProject]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching App projects.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`content`|**Optional\[List\[[AppProject](toloka.client.app.AppProject.md)\]\]**|<p>A list with found App projects.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching App projects.</p> <ul> <li>`True` — There are more matching App projects, not included in `content` due to the limit set in the search request.</li> <li>`False` — `content` contains all matching App projects.</li> </ul>
