# GoldenSetAnswersCount
`toloka.client.conditions.GoldenSetAnswersCount` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L255)

```python
GoldenSetAnswersCount(
    self,
    operator: CompareOperator,
    value: Optional[int] = None
)
```

The number of completed control tasks.


`GoldenSetAnswersCount` is used with collectors:
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
