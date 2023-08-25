# SetSkill
`toloka.client.actions.SetSkill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/actions.py#L171)

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
new_pool = toloka.client.pool.Pool()
new_pool.quality_control.add_action(
    collector=toloka.client.collectors.AnswerCount(),
    conditions=[toloka.client.conditions.AssignmentsAcceptedCount > 0],
    action=toloka.client.actions.SetSkill(skill_id='11294', skill_value=1),
)
```
