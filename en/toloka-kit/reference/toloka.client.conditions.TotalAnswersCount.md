# TotalAnswersCount
`toloka.client.conditions.TotalAnswersCount` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L566)

```python
TotalAnswersCount(
    self,
    operator: CompareOperator,
    value: Optional[int] = None
)
```

The number of completed tasks.


`TotalAnswersCount` is used with collectors:
- [GoldenSet](toloka.client.collectors.GoldenSet.md)
- [MajorityVote](toloka.client.collectors.MajorityVote.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.MajorityVote(answer_threshold=2),
    conditions=[
        toloka.client.conditions.TotalAnswersCount > 9,
        toloka.client.conditions.IncorrectAnswersRate > 60,
    ],
    action=toloka.client.actions.RejectAllAssignments()
)
```
