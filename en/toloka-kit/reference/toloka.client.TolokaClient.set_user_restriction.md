# set_user_restriction
`toloka.client.TolokaClient.set_user_restriction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/__init__.py#L3183)

```python
set_user_restriction(self, user_restriction: UserRestriction)
```

Restricts access to projects or pools for a Toloker.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_restriction`|**[UserRestriction](toloka.client.user_restriction.UserRestriction.md)**|<p>Restriction parameters.</p>

* **Returns:**

  Updated restriction object.

* **Return type:**

  [UserRestriction](toloka.client.user_restriction.UserRestriction.md)

**Examples:**

If a Toloker often makes mistakes, we will restrict access to all our projects.

```python
new_restriction = toloka_client.set_user_restriction(
    toloka.user_restriction.ProjectUserRestriction(
        user_id='1',
        private_comment='The Toloker often makes mistakes',
        project_id='5'
    )
)
```
