# get_skill
`toloka.client.TolokaClient.get_skill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L2256)

```python
get_skill(self, skill_id: str)
```

Gets skill information from Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`skill_id`|**str**|<p>The ID of the skill.</p>

* **Returns:**

  The skill.

* **Return type:**

  [Skill](toloka.client.skill.Skill.md)

**Examples:**


```python
skill = toloka_client.get_skill(skill_id='14486')
```
