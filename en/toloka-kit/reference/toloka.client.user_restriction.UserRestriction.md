# UserRestriction
`toloka.client.user_restriction.UserRestriction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/user_restriction.py#L25)

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

Controls access to projects and pools.


You can restrict access to any project for a Toloker. Then he can't do tasks in the project. You may set the duration of restriction or apply permanent restriction.
To unlock access pass the restriction ID to the `delete_user_restriction`.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**Optional\[str\]**|<p>The ID of the Toloker.</p>
`private_comment`|**Optional\[str\]**|<p>A comment for you why access to this Toloker was restricted.</p>
`will_expire`|**Optional\[datetime\]**|<p>When access is restored. If you do not set the parameter, then the access restriction is permanent.</p>
`id`|**Optional\[str\]**|<p>The identifier of a specific fact of access restriction. Read-only field.</p>
`created`|**Optional\[datetime\]**|<p>Date and time when the fact of access restriction was created. Read-only field.</p>

**Examples:**

How you can lock access for one Toloker on one project.

```python
new_restrict = toloka_client.set_user_restriction(
    ProjectUserRestriction(
        user_id='1',
        private_comment='I dont like you',
        project_id='5'
    )
)
```

And how you can unlock it.

```python
toloka_client.delete_user_restriction(new_restrict.id)
```
