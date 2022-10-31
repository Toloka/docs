# UsersAssessment
`toloka.client.collectors.UsersAssessment` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/collectors.py#L487)

```python
UsersAssessment(self, *, uuid: Optional[UUID] = None)
```

This collector helps you to reassign task suites completed by blocked Tolokers.


The collector can be used with conditions:
* [PoolAccessRevokedReason](toloka.client.conditions.PoolAccessRevokedReason.md) — The reason why the Toloker has lost access to the pool.
* [SkillId](toloka.client.conditions.SkillId.md) — The ID of a skill if reason is `SKILL_CHANGE`.

The collector can be used with actions:
* [ChangeOverlap](toloka.client.actions.ChangeOverlap.md) changes the overlap of a task suite.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`uuid`|**Optional\[UUID\]**|<p>The ID of a collector. Note that when you clone a pool, both pools start using the same collector, because it is not cloned. Usually, it is not an intended behavior. For example, in this case one collector gathers history size from both pools.</p>

**Examples:**

The example shows how to reassign rejected assignments to other Tolokers.

```python
new_pool = toloka.pool.Pool(....)
new_pool.quality_control.add_action(
    collector=toloka.collectors.UsersAssessment(),
    conditions=[toloka.conditions.PoolAccessRevokedReason == toloka.conditions.PoolAccessRevokedReason.RESTRICTION],
    action=toloka.actions.ChangeOverlap(delta=1, open_pool=True),
)
```
