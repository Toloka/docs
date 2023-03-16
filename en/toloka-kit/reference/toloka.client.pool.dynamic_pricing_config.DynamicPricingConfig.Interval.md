# Interval
`toloka.client.pool.dynamic_pricing_config.DynamicPricingConfig.Interval` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/pool/dynamic_pricing_config.py#L27)

```python
Interval(
    self,
    *,
    from_: Optional[int] = None,
    to: Optional[int] = None,
    reward_per_assignment: Optional[float] = None
)
```

Skill level interval with the associated price per task suite.


The lower and upper skill bounds are included in the interval.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`from_`|**Optional\[int\]**|<p>The lower bound of the interval.</p>
`to`|**Optional\[int\]**|<p>The upper bound of the interval.</p>
`reward_per_assignment`|**Optional\[float\]**|<p>The price per task suite for a Toloker with the specified skill level.</p>
