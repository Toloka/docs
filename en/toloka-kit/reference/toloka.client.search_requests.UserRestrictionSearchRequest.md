# UserRestrictionSearchRequest
`toloka.client.search_requests.UserRestrictionSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/search_requests.py#L700)

```python
UserRestrictionSearchRequest(
    self,
    scope: Optional[UserRestriction.Scope] = None,
    user_id: Optional[str] = None,
    project_id: Optional[str] = None,
    pool_id: Optional[str] = None,
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

Parameters for searching Toloker restrictions.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`scope`|**Optional\[[UserRestriction.Scope](toloka.client.user_restriction.UserRestriction.Scope.md)\]**|<p>The scope of a restriction. Refer to the [UserRestriction.Scope](toloka.client.user_restriction.UserRestriction.Scope.md) page for more information on the available `scope` values.</p>
`user_id`|**Optional\[str\]**|<p>The Toloker&#x27;s ID.</p>
`project_id`|**Optional\[str\]**|<p>The ID of a project with restricted access.</p>
`pool_id`|**Optional\[str\]**|<p>The ID of a pool with restricted access.</p>
`id_lt`|**Optional\[str\]**|<p>Restrictions with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Restrictions with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Restrictions with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Restrictions with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Restrictions created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Restrictions created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Restrictions created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Restrictions created after or on the specified date.</p>
