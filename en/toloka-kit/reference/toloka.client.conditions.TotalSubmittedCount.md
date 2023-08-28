# TotalSubmittedCount
`toloka.client.conditions.TotalSubmittedCount` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L611)

```python
TotalSubmittedCount(
    self,
    operator: CompareOperator,
    value: Optional[int] = None
)
```

The number of assignments submitted by a Toloker.


`TotalSubmittedCount` is used with collectors:
- [AssignmentSubmitTime](toloka.client.collectors.AssignmentSubmitTime.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.AssignmentSubmitTime(
        fast_submit_threshold_seconds=20
    ),
    conditions=[toloka.client.conditions.FastSubmittedCount > 3,
        toloka.client.conditions.TotalSubmittedCount <= 5],
    action=toloka.client.actions.RejectAllAssignments()
)
```
