# PoolSearchResult
`toloka.client.search_results.PoolSearchResult`

```python
PoolSearchResult(
    self,
    *,
    items: Optional[List[Pool]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching pools.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[Pool](toloka.client.pool.Pool.md)\]\]**|<p>A list with found pools.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching pools.</p> <ul> <li>`True` — There are more matching pools, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching pools.</li> </ul>
