# get_skill
`toloka.async_client.client.AsyncTolokaClient.get_skill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/async_client/client.py#L0)

```python
async get_skill(self, skill_id: str)
```

Reads one specific skill

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`skill_id`|**str**|<p>ID of the skill.</p>

* **Returns:**

  The skill.

* **Return type:**

  [Skill](toloka.client.skill.Skill.md)

**Examples:**


```python
toloka_client.get_skill(skill_id='1')
```
