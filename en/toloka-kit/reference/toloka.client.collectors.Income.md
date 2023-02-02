# Income
`toloka.client.collectors.Income` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/collectors.py#L363)

```python
Income(self, *, uuid: Optional[UUID] = None)
```

Counts Toloker's daily earnings in the pool.


Helpful when you need to:
- Get responses from as many Tolokers as possible.

The collector can be used with conditions:
* [IncomeSumForLast24Hours](toloka.client.conditions.IncomeSumForLast24Hours.md) — The Toloker earnings for completed tasks in the pool during the last 24 hours.

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

The example shows how to block Toloker's access to the project for 1 day if their earnings reach 1 dollar.

```python
new_pool = toloka.pool.Pool(....)
new_pool.quality_control.add_action(
    collector=toloka.collectors.Income(),
    conditions=[toloka.conditions.IncomeSumForLast24Hours > 1],
    action=toloka.actions.RestrictionV2(
        scope=toloka.user_restriction.UserRestriction.PROJECT,
        duration=1,
        duration_unit='DAYS',
        private_comment='Earnings limit is reached',
    )
)
```
