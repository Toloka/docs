# RejectedAssignmentsRate
`toloka.client.conditions.RejectedAssignmentsRate` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L440)

```python
RejectedAssignmentsRate(
    self,
    operator: CompareOperator,
    value: Optional[float] = None
)
```

A percentage of rejected assignments submitted by a Toloker.


`RejectedAssignmentsRate` is used with collectors:
- [AcceptanceRate](toloka.client.collectors.AcceptanceRate.md)

See also:
- [RejectedAssignmentsCount](toloka.client.conditions.RejectedAssignmentsCount.md) — The number of rejected assignments of a task suite.


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.AcceptanceRate(),
    conditions=[
        toloka.client.conditions.TotalAssignmentsCount > 2,
        toloka.client.conditions.RejectedAssignmentsRate > 40,
    ],
    action=toloka.client.actions.RestrictionV2(
        scope='PROJECT', duration=15, duration_unit='DAYS'
    )
)
```
