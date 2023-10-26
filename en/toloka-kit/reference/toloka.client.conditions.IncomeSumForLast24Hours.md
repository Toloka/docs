# IncomeSumForLast24Hours
`toloka.client.conditions.IncomeSumForLast24Hours` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/conditions.py#L321)

```python
IncomeSumForLast24Hours(
    self,
    operator: CompareOperator,
    value: Optional[float] = None
)
```

The Toloker's earnings for completed tasks in the pool during the last 24 hours.


`IncomeSumForLast24Hours` is used with collectors:
- [Income](toloka.client.collectors.Income.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.quality_control.add_action(
    collector=toloka.client.collectors.Income(),
    conditions=[toloka.client.conditions.IncomeSumForLast24Hours > 0.8],
    action=toloka.client.actions.RestrictionV2(
        scope='PROJECT', duration=1, duration_unit='DAYS',
        private_comment='Earnings limit is reached',
    )
)
```
