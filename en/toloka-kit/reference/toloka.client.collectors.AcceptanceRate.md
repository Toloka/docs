# AcceptanceRate
`toloka.client.collectors.AcceptanceRate` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/collectors.py#L62)

```python
AcceptanceRate(
    self,
    *,
    uuid: Optional[UUID] = None,
    history_size: Optional[int] = None
)
```

Counts accepted and rejected Toloker's assignments.


If non-automatic acceptance is set in the pool, you may use this collector to:
- Set a Toloker's skill.
- Block access for Tolokers with too many rejected responses.

The collector can be used with conditions:
* [TotalAssignmentsCount](toloka.client.conditions.TotalAssignmentsCount.md) — Total count of checked assignments submitted by a Toloker.
* [AcceptedAssignmentsRate](toloka.client.conditions.AcceptedAssignmentsRate.md) — A percentage of accepted assignments.
* [RejectedAssignmentsRate](toloka.client.conditions.RejectedAssignmentsRate.md) — A percentage of rejected assignments.

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
`history_size`|**Optional\[int\]**|<p>The maximum number of recent assignments used to calculate the statistics. If `history_size` is omitted, all Toloker&#x27;s assignments are counted.</p>

**Examples:**

The example shows how to block a Toloker if they make too many mistakes.
If more than 35% of responses are rejected, then the Toloker is restricted to access the project.
The rule is applied after collecting 3 or more responses.

```python
new_pool = toloka.pool.Pool(....)
new_pool.quality_control.add_action(
    collector=toloka.collectors.AcceptanceRate(),
    conditions=[
        toloka.conditions.TotalAssignmentsCount > 2,
        toloka.conditions.RejectedAssignmentsRate > 35,
    ],
    action=toloka.actions.RestrictionV2(
        scope=toloka.user_restriction.UserRestriction.PROJECT,
        duration=15,
        duration_unit='DAYS',
        private_comment='The Toloker often makes mistakes',
    )
)
```
