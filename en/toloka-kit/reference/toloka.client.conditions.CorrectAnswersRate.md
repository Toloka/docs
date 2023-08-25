# CorrectAnswersRate
`toloka.client.conditions.CorrectAnswersRate` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L186)

```python
CorrectAnswersRate(
    self,
    operator: CompareOperator,
    value: Optional[float] = None
)
```

The percentage of correct responses.


`CorrectAnswersRate` is used with collectors:
- [GoldenSet](toloka.client.collectors.GoldenSet.md)
- [MajorityVote](toloka.client.collectors.MajorityVote.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.MajorityVote(answer_threshold=2),
    conditions=[
        toloka.client.conditions.TotalAnswersCount > 9,
        toloka.client.conditions.CorrectAnswersRate < 60,
    ],
    action=toloka.client.actions.RejectAllAssignments(public_comment='Too low quality')
)
```
