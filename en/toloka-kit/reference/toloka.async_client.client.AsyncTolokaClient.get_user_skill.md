# get_user_skill
`toloka.async_client.client.AsyncTolokaClient.get_user_skill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/async_client/client.py#L0)

```python
async get_user_skill(self, user_skill_id: str)
```

Gets the value of a Toloker's skill


`UserSkill` describes the skill value for a specific Toloker.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_skill_id`|**str**|<p>The ID of the Toloker skill.</p>

* **Returns:**

  The skill value.

* **Return type:**

  [UserSkill](toloka.client.user_skill.UserSkill.md)

**Examples:**


```python
toloka_client.get_user_skill(user_skill_id='1')
```
