# SetSkillFromOutputField
`toloka.client.actions.SetSkillFromOutputField` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/actions.py#L98)

```python
SetSkillFromOutputField(
    self,
    *,
    skill_id: Optional[str] = None,
    from_field: Union[RuleConditionKey, str, None] = None
)
```

Sets Toloker's skill value to the percentage of correct or incorrect answers.


You can use this action with [MajorityVote](toloka.client.collectors.MajorityVote.md) and [GoldenSet](toloka.client.collectors.GoldenSet.md) collectors.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`skill_id`|**Optional\[str\]**|<p>The ID of the skill to update.</p>
`from_field`|**Union\[[RuleConditionKey](toloka.client.conditions.RuleConditionKey.md), str, None\]**|<p>The value to assign to the skill:</p> <ul> <li>`correct_answers_rate` — Percentage of correct answers.</li> <li>`incorrect_answers_rate` — Percentage of incorrect answers.</li> </ul>

**Examples:**

In the following example, a `MajorityVote` collector is used to update a skill value.

```python
new_pool = toloka.pool.Pool(....)
new_pool.quality_control.add_action(
    collector=toloka.collectors.MajorityVote(answer_threshold=2, history_size=10),
    conditions=[
        toloka.conditions.TotalAnswersCount > 2,
    ],
    action=toloka.actions.SetSkillFromOutputField(
        skill_id=some_skill_id,
        from_field='correct_answers_rate',
    ),
)
```
