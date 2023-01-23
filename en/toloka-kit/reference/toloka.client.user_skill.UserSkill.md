# UserSkill
`toloka.client.user_skill.UserSkill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/user_skill.py#L29)

```python
UserSkill(
    self,
    *,
    id: Optional[str] = None,
    skill_id: Optional[str] = None,
    user_id: Optional[str] = None,
    value: Optional[int] = None,
    exact_value: Optional[Decimal] = None,
    created: Optional[datetime] = None,
    modified: Optional[datetime] = None
)
```

Describes the value of a specific skill for a specific Toloker.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>Internal identifier of the Toloker&#x27;s skill value.</p>
`skill_id`|**Optional\[str\]**|<p>Skill identifier, which skill is installed.</p>
`user_id`|**Optional\[str\]**|<p>Toloker identifier, to which Toloker the skill is installed.</p>
`value`|**Optional\[int\]**|<p>Skill value (from 0 to 100). Rough presentation.</p>
`exact_value`|**Optional\[Decimal\]**|<p>Skill value (from 0 to 100). Exact representation.</p>
`created`|**Optional\[datetime\]**|<p>Date and time when this skill was created for the Toloker.</p>
`modified`|**Optional\[datetime\]**|<p>Date and time of the last skill change for the Toloker.</p>
