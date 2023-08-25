# MajorityVote
`toloka.client.collectors.MajorityVote` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/collectors.py#L401)

```python
MajorityVote(
    self,
    *,
    uuid: Optional[UUID] = None,
    answer_threshold: Optional[int] = None,
    history_size: Optional[int] = None
)
```

Counts correct responses determined by the majority vote method.


A response chosen by the majority is considered to be correct, and other responses are considered to be incorrect.
Depending on the percentage of correct responses, you can either increase a Toloker's skill value, or to block the Toloker.

The collector can be used with conditions:
* [TotalAnswersCount](toloka.client.conditions.TotalAnswersCount.md) — The number of completed tasks by the Toloker.
* [CorrectAnswersRate](toloka.client.conditions.CorrectAnswersRate.md) — The percentage of correct responses.
* [IncorrectAnswersRate](toloka.client.conditions.IncorrectAnswersRate.md) — The percentage of incorrect responses.

The collector can be used with actions:
* [RestrictionV2](toloka.client.actions.RestrictionV2.md) blocks access to projects or pools.
* [ApproveAllAssignments](toloka.client.actions.ApproveAllAssignments.md) accepts all Toloker's assignments.
* [RejectAllAssignments](toloka.client.actions.RejectAllAssignments.md) rejects all Toloker's assignments.
* [SetSkill](toloka.client.actions.SetSkill.md) sets Toloker's skill value.
* [SetSkillFromOutputField](toloka.client.actions.SetSkillFromOutputField.md) sets Toloker's skill value using an output field.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`uuid`|**Optional\[UUID\]**|<p>The ID of a collector. Note that when you clone a pool, both pools start using the same collector, because it is not cloned. Usually, it is not an intended behavior. For example, in this case one collector gathers history size from both pools.</p>
`answer_threshold`|**Optional\[int\]**|<p>The number of Tolokers considered the majority.</p>
`history_size`|**Optional\[int\]**|<p>The maximum number of recent Toloker&#x27;s responses to calculate the statistics. If it is omitted, calculation is based on all collected responses.</p>

**Examples:**

The example shows how to reject all Toloker's responses if they significantly differ from the majority. The rule is applied after collecting at least 10 responses.

```python
new_pool = toloka.client.pool.Pool()
new_pool.quality_control.add_action(
    collector=toloka.client.collectors.MajorityVote(answer_threshold=2),
    conditions=[
        toloka.client.conditions.TotalAnswersCount > 9,
        toloka.client.conditions.CorrectAnswersRate < 60,
    ],
    action=toloka.client.actions.RejectAllAssignments(public_comment='Too low quality')
)
```
