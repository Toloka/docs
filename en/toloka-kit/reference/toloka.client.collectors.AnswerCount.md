# AnswerCount
`toloka.client.collectors.AnswerCount` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/collectors.py#L130)

```python
AnswerCount(self, *, uuid: Optional[UUID] = None)
```

Counts assignments submitted by a Toloker.


Collector use cases.
- To involve as many Tolokers as possible limit assignments to 1.
- To improve protection from robots set the limit higher, such as 10% of the pool's tasks.
- You can filter Tolokers who complete your tasks, so they don't check the tasks in the checking project.

The collector can be used with conditions:
* [AssignmentsAcceptedCount](toloka.client.conditions.AssignmentsAcceptedCount.md) — The number of accepted assignments.

The collector can be used with actions:
* [RestrictionV2](toloka.client.actions.RestrictionV2.md) blocks access to projects or pools.
* [ApproveAllAssignments](toloka.client.actions.ApproveAllAssignments.md) accepts all Toloker's assignments.
* [RejectAllAssignments](toloka.client.actions.RejectAllAssignments.md) rejects all Toloker's assignments.
* [SetSkill](toloka.client.actions.SetSkill.md) sets Toloker's skill value.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`uuid`|**Optional\[UUID\]**|<p>The ID of a collector. Note that when you clone a pool, both pools start using the same collector, because it is not cloned. Usually, it is not an intended behavior. For example, in this case one collector gathers history size from both pools.</p>

**Examples:**

The example shows how to mark Tolokers completing any task in the pool so that you can filter them later in the checking project.

```python
new_pool = toloka.client.pool.Pool()
new_pool.quality_control.add_action(
    collector=toloka.client.collectors.AnswerCount(),
    conditions=[toloka.client.conditions.AssignmentsAcceptedCount > 0],
    action=toloka.client.actions.SetSkill(skill_id='11294', skill_value=1),
)
```
