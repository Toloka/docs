# SkillSearchResult
`toloka.client.search_results.SkillSearchResult`

```python
SkillSearchResult(
    self,
    *,
    items: Optional[List[Skill]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching skills.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[Skill](toloka.client.skill.Skill.md)\]\]**|<p>A list with found skills.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching skills.</p> <ul> <li>`True` — There are more matching skills, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching skills.</li> </ul>
