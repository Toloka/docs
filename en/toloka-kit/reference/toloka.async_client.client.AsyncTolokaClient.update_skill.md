# update_skill
`toloka.async_client.client.AsyncTolokaClient.update_skill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/async_client/client.py#L0)

```python
async update_skill(
    self,
    skill_id: str,
    skill: Skill
)
```

Updates all skill parameters in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`skill_id`|**str**|<p>The ID of the skill to be updated.</p>
`skill`|**[Skill](toloka.client.skill.Skill.md)**|<p>The skill with new parameters.</p>

* **Returns:**

  The skill with updated parameters.

* **Return type:**

  [Skill](toloka.client.skill.Skill.md)

**Examples:**


```python
updated_skill = toloka_client.get_skill(skill_id='14486')
updated_skill.hidden = False
toloka_client.update_skill(skill_id=updated_skill.id, skill=updated_skill)
```
