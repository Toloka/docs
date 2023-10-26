# FailRate
`toloka.client.conditions.FailRate` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/conditions.py#L209)

```python
FailRate(
    self,
    operator: CompareOperator,
    value: Optional[float] = None
)
```

Deprecated. The percentage of unsolved captchas.


`FailRate` is used with collectors:
- [Captcha](toloka.client.collectors.Captcha.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.set_captcha_frequency('MEDIUM')
pool.quality_control.add_action(
    collector=toloka.client.collectors.Captcha(history_size=5),
    conditions=[
        toloka.client.conditions.FailRate > 40,
        toloka.client.conditions.StoredResultsCount >= 3
    ],
    action=toloka.client.actions.RestrictionV2(
        scope='PROJECT', duration=15, duration_unit='DAYS'
    )
)
```
