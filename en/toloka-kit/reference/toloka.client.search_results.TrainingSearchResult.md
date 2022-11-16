# TrainingSearchResult
`toloka.client.search_results.TrainingSearchResult`

```python
TrainingSearchResult(
    self,
    *,
    items: Optional[List[Training]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching training pools.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[Training](toloka.client.training.Training.md)\]\]**|<p>A list with found training pools.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching training pools.</p> <ul> <li>`True` — There are more matching training pools, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching training pools.</li> </ul>
