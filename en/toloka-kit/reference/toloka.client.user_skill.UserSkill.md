# UserSkill
`toloka.client.user_skill.UserSkill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/user_skill.py#L28)

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

A Toloker's skill value.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the Toloker&#x27;s skill value.</p>
`user_id`|**Optional\[str\]**|<p>The ID of the Toloker.</p>
`skill_id`|**Optional\[str\]**|<p>The ID of the skill.</p>
`exact_value`|**Optional\[Decimal\]**|<p>The fractional value of the skill. Allowed values: from 0 to 100.</p>
`value`|**Optional\[int\]**|<p>The value of the skill rounded to the nearest integer.</p>
`created`|**Optional\[datetime\]**|<p>The date and time when the skill was assigned the first time.</p>
`modified`|**Optional\[datetime\]**|<p>The date and time when the skill value was updated.</p>
