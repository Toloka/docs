# DynamicPricingConfig
`toloka.client.pool.dynamic_pricing_config.DynamicPricingConfig` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/pool/dynamic_pricing_config.py#L9)

```python
DynamicPricingConfig(
    self,
    type: Union[Type, str, None] = None,
    skill_id: Optional[str] = None,
    intervals: Optional[List[Interval]] = None
)
```

The dynamic pricing settings.


A price per task suite can be variable depending on a Toloker's skill.
If a Toloker is not covered by dynamic pricing settings then the default price is used. It is set in the `reward_per_assignment` pool parameter.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`type`|**Optional\[[Type](toloka.client.pool.dynamic_pricing_config.DynamicPricingConfig.Type.md)\]**|<p>The dynamic pricing type. Only `SKILL` type is supported now.</p>
`skill_id`|**Optional\[str\]**|<p>The ID of the skill that dynamic pricing is based on.</p>
`intervals`|**Optional\[List\[[Interval](toloka.client.pool.dynamic_pricing_config.DynamicPricingConfig.Interval.md)\]\]**|<p>A list of skill intervals and prices. The intervals must not overlap.</p>
