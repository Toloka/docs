# update_skill
`toloka.async_client.client.AsyncTolokaClient.update_skill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/async_client/client.py#L0)

```python
async update_skill(
    self,
    skill_id: str,
    skill: Skill
)
```

Makes changes to the skill

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`skill_id`|**str**|<p>ID of the training that will be changed.</p>
`skill`|**[Skill](toloka.client.skill.Skill.md)**|<p>A skill object with all the fields: those that will be updated and those that will not.</p>

* **Returns:**

  Modified skill object with all fields.

* **Return type:**

  [Skill](toloka.client.skill.Skill.md)

**Examples:**


```python
toloka_client.update_skill(skill_id=old_skill_id, skill=new_skill_object)
```
