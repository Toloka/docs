# SetUserSkillRequest
`toloka.client.user_skill.SetUserSkillRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/user_skill.py#L12)

```python
SetUserSkillRequest(
    self,
    *,
    skill_id: Optional[str] = None,
    user_id: Optional[str] = None,
    value: Optional[Decimal] = None
)
```

Parameters for setting a skill value for a Toloker.


These parameters are used by the [set_user_skill](toloka.client.TolokaClient.set_user_skill.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**Optional\[str\]**|<p>The Toloker&#x27;s ID.</p>
`skill_id`|**Optional\[str\]**|<p>The ID of the skill to set.</p>
`value`|**Optional\[Decimal\]**|<p>The value of the skill. Allowed values: from 0 to 100.</p>
