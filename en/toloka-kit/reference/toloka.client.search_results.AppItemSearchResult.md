# AppItemSearchResult
`toloka.client.search_results.AppItemSearchResult`

```python
AppItemSearchResult(
    self,
    *,
    content: Optional[List[AppItem]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching App task items.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`content`|**Optional\[List\[[AppItem](toloka.client.app.AppItem.md)\]\]**|<p>A list with found task items.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching task items.</p> <ul> <li>`True` — There are more matching task items, not included in `content` due to the limit set in the search request.</li> <li>`False` — `content` contains all matching task items.</li> </ul>
