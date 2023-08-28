# delete_user_skill
`toloka.client.TolokaClient.delete_user_skill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3562)

```python
delete_user_skill(self, user_skill_id: str)
```

Removes a skill from a Toloker.


Tolokers' skill values are described by the [UserSkill](toloka.client.user_skill.UserSkill.md) class.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_skill_id`|**str**|<p>The ID of the Toloker's skill value.</p>

**Examples:**


```python
toloka_client.delete_user_skill(user_skill_id='54118009')
```
