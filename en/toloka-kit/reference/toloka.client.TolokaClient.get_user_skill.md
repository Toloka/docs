# get_user_skill
`toloka.client.TolokaClient.get_user_skill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3474)

```python
get_user_skill(self, user_skill_id: str)
```

Gets the value of a Toloker's skill.


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
user_skill = toloka_client.get_user_skill(user_skill_id='54118009')
print(user_skill.value)
```
