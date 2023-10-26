# GoldenSetCorrectAnswersRate
`toloka.client.conditions.GoldenSetCorrectAnswersRate` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/conditions.py#L277)

```python
GoldenSetCorrectAnswersRate(
    self,
    operator: CompareOperator,
    value: Optional[float] = None
)
```

The percentage of correct responses to control tasks.


`GoldenSetCorrectAnswersRate` is used with collectors:
- [GoldenSet](toloka.client.collectors.GoldenSet.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.GoldenSet(history_size=5),
    conditions=[
        toloka.client.conditions.GoldenSetCorrectAnswersRate > 80,
        toloka.client.conditions.GoldenSetAnswersCount >= 5,
    ],
    action=toloka.client.actions.ApproveAllAssignments()
)
```
