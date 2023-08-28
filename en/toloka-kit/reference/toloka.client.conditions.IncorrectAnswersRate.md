# IncorrectAnswersRate
`toloka.client.conditions.IncorrectAnswersRate` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L343)

```python
IncorrectAnswersRate(
    self,
    operator: CompareOperator,
    value: Optional[float] = None
)
```

The percentage of incorrect responses.


`IncorrectAnswersRate` is used with collectors:
- [MajorityVote](toloka.client.collectors.MajorityVote.md)
- [GoldenSet](toloka.client.collectors.GoldenSet.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.MajorityVote(answer_threshold=2),
    conditions=[
        toloka.client.conditions.TotalAnswersCount > 9,
        toloka.client.conditions.IncorrectAnswersRate > 60,
    ],
    action=toloka.client.actions.RejectAllAssignments(public_comment='Too low quality')
)
```
