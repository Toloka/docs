# SystemUserRestriction
`toloka.client.user_restriction.SystemUserRestriction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/user_restriction.py#L114)

```python
SystemUserRestriction(
    self,
    *,
    user_id: Optional[str] = None,
    private_comment: Optional[str] = None,
    will_expire: Optional[datetime] = None,
    id: Optional[str] = None,
    created: Optional[datetime] = None
)
```

DEPRECATED

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**Optional\[str\]**|<p>The ID of the Toloker.</p>
`private_comment`|**Optional\[str\]**|<p>A comment for you why access to this Toloker was restricted.</p>
`will_expire`|**Optional\[datetime\]**|<p>When access is restored. If you do not set the parameter, then the access restriction is permanent.</p>
`id`|**Optional\[str\]**|<p>The identifier of a specific fact of access restriction. Read-only field.</p>
`created`|**Optional\[datetime\]**|<p>Date and time when the fact of access restriction was created. Read-only field.</p>
