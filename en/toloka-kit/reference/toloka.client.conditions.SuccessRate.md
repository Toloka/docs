# SuccessRate
`toloka.client.conditions.SuccessRate` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/conditions.py#L541)

```python
SuccessRate(
    self,
    operator: CompareOperator,
    value: Optional[float] = None
)
```

Deprecated. A percentage of solved captchas out of all entered captchas.


`SuccessRate` is used with collectors:
- [Captcha](toloka.client.collectors.Captcha.md)


**Examples:**


```python
pool = toloka.client.pool.Pool()
pool.set_captcha_frequency('MEDIUM')
pool.quality_control.add_action(
    collector=toloka.client.collectors.Captcha(history_size=5),
    conditions=[
        toloka.client.conditions.SuccessRate < 40,
        toloka.client.conditions.StoredResultsCount >= 3
    ],
    action=toloka.client.actions.RestrictionV2(
        scope='PROJECT', duration=15, duration_unit='DAYS'
    )
)
```
