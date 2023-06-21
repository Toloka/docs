# GoldenSet
`toloka.client.collectors.GoldenSet` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/collectors.py#L303)

```python
GoldenSet(
    self,
    *,
    uuid: Optional[UUID] = None,
    history_size: Optional[int] = None
)
```

Collects control and training task statistics for a Toloker.


Use control tasks to assign a skill to Tolokers based on their responses and block Tolokers who submit incorrect responses.

It is better **not** to use this collector if:
- There are a lot of response options.
- Tolokers need to attach files to assignments.
- Tolokers need to transcribe text.
- Tolokers need to select objects on a photo.
- Tasks don't have a correct or incorrect responses. For example, you ask about Toloker preferences.

The collector can be used with conditions:
* [TotalAnswersCount](toloka.client.conditions.TotalAnswersCount.md) — The number of completed control and training tasks.
* [CorrectAnswersRate](toloka.client.conditions.CorrectAnswersRate.md) — The percentage of correct responses to control and training tasks.
* [IncorrectAnswersRate](toloka.client.conditions.IncorrectAnswersRate.md) — The percentage of incorrect responses to control and training tasks.
* [GoldenSetAnswersCount](toloka.client.conditions.GoldenSetAnswersCount.md) — The number of completed control tasks.
* [GoldenSetCorrectAnswersRate](toloka.client.conditions.GoldenSetCorrectAnswersRate.md) — The percentage of correct responses to control tasks.
* [GoldenSetIncorrectAnswersRate](toloka.client.conditions.GoldenSetIncorrectAnswersRate.md) — The percentage of incorrect responses to control tasks.

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
`history_size`|**Optional\[int\]**|<p>The maximum number of recent control or training tasks used to calculate the statistics. If `history_size` is omitted, all Toloker&#x27;s control or training tasks in the pool are counted.</p>

**Examples:**

The example shows how to accept all assignments if more than 80% of responses to control tasks are correct.

```python
new_pool = toloka.pool.Pool(....)
new_pool.quality_control.add_action(
    collector=toloka.collectors.GoldenSet(history_size=5),
    conditions=[
        toloka.conditions.GoldenSetCorrectAnswersRate > 80,
        toloka.conditions.GoldenSetAnswersCount >= 5,
    ],
    action=toloka.actions.ApproveAllAssignments()
)
```
