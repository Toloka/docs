# AggregatedSolutionSearchResult
`toloka.client.search_results.AggregatedSolutionSearchResult`

```python
AggregatedSolutionSearchResult(
    self,
    *,
    items: Optional[List[AggregatedSolution]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching aggregated responses.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[AggregatedSolution](toloka.client.aggregation.AggregatedSolution.md)\]\]**|<p>A list with found aggregated responses.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching aggregated responses.</p> <ul> <li>`True` — There are more matching aggregated responses, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching aggregated responses.</li> </ul>
