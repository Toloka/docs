# UserSkillSearchRequest
`toloka.client.search_requests.UserSkillSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/search_requests.py#L650)

```python
UserSkillSearchRequest(
    self,
    user_id: Optional[str] = None,
    skill_id: Optional[str] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None,
    modified_lt: Optional[datetime] = None,
    modified_lte: Optional[datetime] = None,
    modified_gt: Optional[datetime] = None,
    modified_gte: Optional[datetime] = None
)
```

Parameters for searching Toloker skill.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**Optional\[str\]**|<p>The ID of a Toloker.</p>
`skill_id`|**Optional\[str\]**|<p>The ID of a skill.</p>
`id_lt`|**Optional\[str\]**|<p>Skills with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Skills with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Skills with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Skills with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Skills created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Skills created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Skills created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Skills created on or after the specified date.</p>
`modified_lt`|**Optional\[datetime\]**|<p>Skills that changed before the specified date.</p>
`modified_lte`|**Optional\[datetime\]**|<p>Skills that changed before the specified date.</p>
`modified_gt`|**Optional\[datetime\]**|<p>Skills changed after the specified date.</p>
`modified_gte`|**Optional\[datetime\]**|<p>Skills created on or after the specified date.</p>
