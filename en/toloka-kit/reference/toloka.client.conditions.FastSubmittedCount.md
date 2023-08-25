# FastSubmittedCount
`toloka.client.conditions.FastSubmittedCount` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L234)

```python
FastSubmittedCount(
    self,
    operator: CompareOperator,
    value: Optional[int] = None
)
```

The number of assignments completed by a Toloker too fast.


`FastSubmittedCount` is used with collectors:
- [AssignmentSubmitTime](toloka.client.collectors.AssignmentSubmitTime.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.AssignmentSubmitTime(
        history_size=5, fast_submit_threshold_seconds=20
    ),
    conditions=[toloka.client.conditions.FastSubmittedCount > 3],
    action=toloka.client.actions.RejectAllAssignments(public_comment='Too fast responses.')
)
```
