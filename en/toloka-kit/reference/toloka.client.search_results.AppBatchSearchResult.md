# AppBatchSearchResult
`toloka.client.search_results.AppBatchSearchResult`

```python
AppBatchSearchResult(
    self,
    *,
    content: Optional[List[AppBatch]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching batches in an App project.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`content`|**Optional\[List\[[AppBatch](toloka.client.app.AppBatch.md)\]\]**|<p>A list with found batches.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching batches.</p> <ul> <li>`True` — There are more matching batches, not included in `content` due to the limit set in the search request.</li> <li>`False` — `content` contains all matching batches.</li> </ul>
