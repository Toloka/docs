# UserRestriction
`toloka.client.user_restriction.UserRestriction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/user_restriction.py#L25)

```python
UserRestriction(
    self,
    *,
    user_id: Optional[str] = None,
    private_comment: Optional[str] = None,
    will_expire: Optional[datetime] = None,
    id: Optional[str] = None,
    created: Optional[datetime] = None
)
```

A base class for access restrictions.


Toloker's access to projects or pools can be restricted.
You can set the duration of the ban or apply an unlimited restriction.

Use the [set_user_restriction](toloka.client.TolokaClient.set_user_restriction.md) method to apply a restriction
and the [delete_user_restriction](toloka.client.TolokaClient.delete_user_restriction.md) method to remove it.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the restriction.</p>
`user_id`|**Optional\[str\]**|<p>The ID of the Toloker.</p>
`private_comment`|**Optional\[str\]**|<p>A comment visible to the requester only.</p>
`will_expire`|**Optional\[datetime\]**|<p>The UTC date and time when the access will be restored by Toloka. If the parameter isn&#x27;t set, then the restriction is active until you remove it calling the `delete_user_restriction` method.</p>
`created`|**Optional\[datetime\]**|<p>The UTC date and time when the restriction was applied. Read-only field.</p>

**Examples:**

Restricting access to a project and removing the restriction.

```python
new_restriction = toloka_client.set_user_restriction(
    toloka.client.user_restriction.ProjectUserRestriction(
        user_id='1ad097faba0eff85a04fe30bc04d53db',
        private_comment='Low response quality',
        project_id='5'
    )
)
toloka_client.delete_user_restriction(new_restriction.id)
```
