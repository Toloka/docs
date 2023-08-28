# GoldenSetIncorrectAnswersRate
`toloka.client.conditions.GoldenSetIncorrectAnswersRate` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L299)

```python
GoldenSetIncorrectAnswersRate(
    self,
    operator: CompareOperator,
    value: Optional[float] = None
)
```

The percentage of incorrect responses to control tasks.


`GoldenSetIncorrectAnswersRate` is used with collectors:
- [GoldenSet](toloka.client.collectors.GoldenSet.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.GoldenSet(history_size=5),
    conditions=[
        toloka.client.conditions.GoldenSetIncorrectAnswersRate >= 40,
        toloka.client.conditions.GoldenSetAnswersCount >= 5,
    ],
    action=toloka.client.actions.RejectAllAssignments()
)
```
