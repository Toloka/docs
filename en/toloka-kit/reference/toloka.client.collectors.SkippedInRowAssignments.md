# SkippedInRowAssignments
`toloka.client.collectors.SkippedInRowAssignments` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/collectors.py#L452)

```python
SkippedInRowAssignments(self, *, uuid: Optional[UUID] = None)
```

Counts task suites skipped in a row by a Toloker.


Skipping tasks is considered an indirect indicator of quality of responses. You can block access to a pool or project if a Toloker skips multiple task suites in a row.

The collector can be used with conditions:
* [SkippedInRowCount](toloka.client.conditions.SkippedInRowCount.md) — How many tasks in a row a Toloker skipped.

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

The example shows how to block Toloker's access to the project for 15 days if he skipped more than 3 task suites in a row.

```python
new_pool = toloka.client.pool.Pool()
new_pool.quality_control.add_action(
    collector=toloka.client.collectors.SkippedInRowAssignments(),
    conditions=[toloka.client.conditions.SkippedInRowCount > 3],
    action=toloka.client.actions.RestrictionV2(
        scope=toloka.client.user_restriction.UserRestriction.PROJECT,
        duration=15,
        duration_unit='DAYS',
        private_comment='Skips too many task suites in a row',
    )
)
```
