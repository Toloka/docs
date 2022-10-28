# UserRestrictionSearchResult
`toloka.client.search_results.UserRestrictionSearchResult`

```python
UserRestrictionSearchResult(
    self,
    *,
    items: Optional[List[UserRestriction]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching Toloker restrictions.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[UserRestriction](toloka.client.user_restriction.UserRestriction.md)\]\]**|<p>A list with found Toloker restrictions.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching Toloker restrictions.</p> <ul> <li>`True` — There are more matching Toloker restrictions, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching Toloker restrictions.</li> </ul>
