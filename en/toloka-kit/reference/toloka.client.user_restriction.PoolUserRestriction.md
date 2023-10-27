# PoolUserRestriction
`toloka.client.user_restriction.PoolUserRestriction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/user_restriction.py#L96)

```python
PoolUserRestriction(
    self,
    *,
    user_id: Optional[str] = None,
    private_comment: Optional[str] = None,
    will_expire: Optional[datetime] = None,
    id: Optional[str] = None,
    created: Optional[datetime] = None,
    pool_id: Optional[str] = None
)
```

A pool restriction.


A Toloker doesn't have access to the pool.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**Optional\[str\]**|<p>The ID of the Toloker.</p>
`private_comment`|**Optional\[str\]**|<p>A comment visible to the requester only.</p>
`will_expire`|**Optional\[datetime\]**|<p>The UTC date and time when the access will be restored by Toloka. If the parameter isn&#x27;t set, then the restriction is active until you remove it calling the `delete_user_restriction` method.</p>
`id`|**Optional\[str\]**|<p>The ID of the restriction.</p>
`created`|**Optional\[datetime\]**|<p>The UTC date and time when the restriction was applied. Read-only field.</p>
`pool_id`|**Optional\[str\]**|<p>The ID of the pool that is blocked.</p>
