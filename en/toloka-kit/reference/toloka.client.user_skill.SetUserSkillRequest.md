# SetUserSkillRequest
`toloka.client.user_skill.SetUserSkillRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/user_skill.py#L12)

```python
SetUserSkillRequest(
    self,
    *,
    skill_id: Optional[str] = None,
    user_id: Optional[str] = None,
    value: Optional[Decimal] = None
)
```

Parameters for setting the skill value of a specific Toloker.


Used for grouping the fields required for setting the Toloker's skill.
Usually, when calling TolokaClient.set_user_skill, you can use the expand version, passing all the class attributes to the call.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`skill_id`|**Optional\[str\]**|<p>Skill ID. What skill to set.</p>
`user_id`|**Optional\[str\]**|<p>Toloker&#x27;s ID.</p>
`value`|**Optional\[Decimal\]**|<p>Fractional value of the skill. Minimum - 0, maximum - 100.</p>
