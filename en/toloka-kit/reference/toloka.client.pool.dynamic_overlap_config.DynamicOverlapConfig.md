# DynamicOverlapConfig
`toloka.client.pool.dynamic_overlap_config.DynamicOverlapConfig` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/pool/dynamic_overlap_config.py#L9)

```python
DynamicOverlapConfig(
    self,
    *,
    type: Union[Type, str, None] = None,
    max_overlap: Optional[int] = None,
    min_confidence: Optional[float] = None,
    answer_weight_skill_id: Optional[str] = None,
    fields: Optional[List[Field]] = None
)
```

Dynamic overlap settings.


Toloka can automatically increase an overlap of tasks if the confidence level of aggregated responses is not high enough.

Dynamic overlap uses the `BASIC` algorithm.
Each response is assigned a weight depending on the Toloker's skill value.
The aggregated response confidence is calculated based on the probability algorithm.
The task overlap increases until it reaches `max_overlap` or until the confidence of the aggregated response exceeds `min_confidence`.

Note, that if you use dynamic overlap, then set the `auto_close_after_complete_delay_seconds` pool parameter to a non zero value.

Learn more about the [Dynamic overlap](https://toloka.ai/en/docs/guide/concepts/dynamic-overlap) in the guide.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`type`|**Optional\[[Type](toloka.client.pool.dynamic_overlap_config.DynamicOverlapConfig.Type.md)\]**|<p>The dynamic overlap algorithm.</p>
`max_overlap`|**Optional\[int\]**|<p>Maximum overlap. The value must be higher than the default overlap value. Allowed range: from 1 to 30,000.</p>
`min_confidence`|**Optional\[float\]**|<p>Minimum required confidence of the aggregated response. Allowed range: from 0 to 1.</p>
`answer_weight_skill_id`|**Optional\[str\]**|<p>A skill that determines the weight of the Toloker&#x27;s responses. For the best results, use a skill calculated as a percentage of correct responses in control tasks.</p>
`fields`|**Optional\[List\[[Field](toloka.client.pool.dynamic_overlap_config.DynamicOverlapConfig.Field.md)\]\]**|<p>A list of output data fields used for aggregating responses. For the best results, each field must have a limited number of response options. Don&#x27;t specify fields in the list together if they depend on each other.</p>
