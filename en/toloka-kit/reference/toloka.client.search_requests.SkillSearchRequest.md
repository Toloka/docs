# SkillSearchRequest
`toloka.client.search_requests.SkillSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/search_requests.py#L325)

```python
SkillSearchRequest(
    self,
    name: Optional[str] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None
)
```

Parameters for searching skill.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`name`|**Optional\[str\]**|<p>The name of the skill.</p>
`id_lt`|**Optional\[str\]**|<p>Skills with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Skills with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Skills with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Skills with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Skills created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Skills created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Skills created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Skills created on or after the specified date.</p>
