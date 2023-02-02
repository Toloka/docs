# delete_user_skill
`toloka.async_client.client.AsyncTolokaClient.delete_user_skill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/async_client/client.py#L0)

```python
async delete_user_skill(self, user_skill_id: str)
```

Drop specific UserSkill


`UserSkill` describes the skill value for a specific Toloker.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_skill_id`|**str**|<p>ID of the fact that the Toloker has a skill to delete.</p>

**Examples:**


```python
toloka_client.delete_user_skill(user_skill_id='1')
```
