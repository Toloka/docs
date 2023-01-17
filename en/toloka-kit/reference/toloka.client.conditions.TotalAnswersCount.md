# TotalAnswersCount
`toloka.client.conditions.TotalAnswersCount` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/conditions.py#L343)

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

