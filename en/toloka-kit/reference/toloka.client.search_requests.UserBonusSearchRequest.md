# UserBonusSearchRequest
`toloka.client.search_requests.UserBonusSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/search_requests.py#L750)

```python
UserBonusSearchRequest(
    self,
    user_id: Optional[str] = None,
    assignment_id: Optional[str] = None,
    private_comment: Optional[str] = None,
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

Parameters for searching Tolokers' rewards.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**Optional\[str\]**|<p>The ID of a Toloker.</p>
`assignment_id`|**Optional\[str\]**|<p>The ID of an assignment a reward was granted for.</p>
`private_comment`|**Optional\[str\]**|<p>Rewards with specified comment.</p>
`id_lt`|**Optional\[str\]**|<p>Rewards with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Rewards with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Rewards with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Rewards with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Rewards given before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Rewards given before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Rewards given after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Rewards given after or on the specified date.</p>
