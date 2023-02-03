# SetSkill
`toloka.client.actions.SetSkill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/actions.py#L159)

```python
SetSkill(
    self,
    *,
    skill_id: Optional[str] = None,
    skill_value: Optional[int] = None
)
```

Sets Toloker's skill value.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`skill_id`|**Optional\[str\]**|<p>The ID of the skill.</p>
`skill_value`|**Optional\[int\]**|<p>The new value of the skill.</p>

**Examples:**

When an answer is accepted, the Toloker gets a skill. Later you can filter Tolokers by that skill.

```python
new_pool = toloka.pool.Pool(....)
new_pool.quality_control.add_action(
    collector=toloka.collectors.AnswerCount(),
    conditions=[toloka.conditions.AssignmentsAcceptedCount > 0],
    action=toloka.actions.SetSkill(skill_id=some_skill_id, skill_value=1),
)
```
