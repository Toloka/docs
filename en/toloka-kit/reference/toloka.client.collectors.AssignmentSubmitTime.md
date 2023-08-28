# AssignmentSubmitTime
`toloka.client.collectors.AssignmentSubmitTime` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/collectors.py#L203)

```python
AssignmentSubmitTime(
    self,
    *,
    uuid: Optional[UUID] = None,
    fast_submit_threshold_seconds: Optional[int] = None,
    history_size: Optional[int] = None
)
```

Counts fast responses.


Collector use cases.
- To find Tolokers who respond suspiciously quickly.
- To improve protection against robots.

The collector can be used with conditions:
* [TotalSubmittedCount](toloka.client.conditions.TotalSubmittedCount.md) — The number of assignments completed by a specific Toloker.
* [FastSubmittedCount](toloka.client.conditions.FastSubmittedCount.md) — The number of assignments completed too fast.

The collector can be used with actions:
* [RestrictionV2](toloka.client.actions.RestrictionV2.md) blocks access to projects or pools.
* [ApproveAllAssignments](toloka.client.actions.ApproveAllAssignments.md) accepts all Toloker's assignments.
* [RejectAllAssignments](toloka.client.actions.RejectAllAssignments.md) rejects all Toloker's assignments.
* [SetSkill](toloka.client.actions.SetSkill.md) sets Toloker's skill value.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`uuid`|**Optional\[UUID\]**|<p>The ID of a collector. Note that when you clone a pool, both pools start using the same collector, because it is not cloned. Usually, it is not an intended behavior. For example, in this case one collector gathers history size from both pools.</p>
`fast_submit_threshold_seconds`|**Optional\[int\]**|<p>Fast response threshold in seconds. Any response submitted in less time than threshold is considered a fast response.</p>
`history_size`|**Optional\[int\]**|<p>The maximum number of recent assignments used to calculate the statistics. If `history_size` is omitted, all Toloker's assignments in the pool are counted.</p>

**Examples:**

The example shows how to reject all assignments if a Toloker sent at least 4 responses during 20 seconds after getting every task suite.

```python
new_pool = toloka.client.pool.Pool()
new_pool.quality_control.add_action(
    collector=toloka.client.collectors.AssignmentSubmitTime(history_size=5, fast_submit_threshold_seconds=20),
    conditions=[toloka.client.conditions.FastSubmittedCount > 3],
    action=toloka.client.actions.RejectAllAssignments(public_comment='Too fast responses.')
)
```
