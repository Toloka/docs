# RejectedAssignmentsRate
`toloka.client.conditions.RejectedAssignmentsRate` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/conditions.py#L284)

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

