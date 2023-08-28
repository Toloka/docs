# AcceptedAssignmentsCount
`toloka.client.conditions.AcceptedAssignmentsCount` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L82)

```python
AcceptedAssignmentsCount(
    self,
    operator: CompareOperator,
    value: Optional[int] = None
)
```

The number of accepted assignments of a task suite.


`AcceptedAssignmentsCount` is used with collectors:
- [AssignmentsAssessment](toloka.client.collectors.AssignmentsAssessment.md)

See also:
- [AssignmentsAcceptedCount](toloka.client.conditions.AssignmentsAcceptedCount.md) — The number of assignments accepted from a Toloker.


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.AssignmentsAssessment(),
    conditions=[toloka.client.conditions.AcceptedAssignmentsCount < toloka.client.conditions.RejectedAssignmentsCount],
    action=toloka.client.actions.ChangeOverlap(delta=1, open_pool=True),
)
```
