# AppSearchResult
`toloka.client.search_results.AppSearchResult`

```python
AppSearchResult(
    self,
    *,
    content: Optional[List[App]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching App solutions.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`content`|**Optional\[List\[[App](toloka.client.app.App.md)\]\]**|<p>A list with found App solutions.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching App solutions.</p> <ul> <li>`True` — There are more matching App solutions, not included in `content` due to the limit set in the search request.</li> <li>`False` — `content` contains all matching App solutions.</li> </ul>
