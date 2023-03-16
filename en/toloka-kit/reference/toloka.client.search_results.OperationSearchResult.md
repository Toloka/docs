# OperationSearchResult
`toloka.client.search_results.OperationSearchResult`

```python
OperationSearchResult(
    self,
    *,
    items: Optional[List[Operation]] = None,
    has_more: Optional[bool] = None
)
```

The list of found operations and whether there is something else on the original request


It's better to use TolokaClient.get_operations(),
which already implements the correct handling of the search result.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[Operation](toloka.client.operations.Operation.md)\]\]**|<p>List of found operations</p>
`has_more`|**Optional\[bool\]**|<p>Whether the list is complete:</p> <ul> <li>`True` — Not all elements are included in the output due to restrictions in the limit parameter.</li> <li>`False` — The output lists all the items.</li> </ul>
