# RuleConfig
`toloka.client.quality_control.QualityControl.QualityControlConfig.RuleConfig` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/quality_control.py#L109)

```python
RuleConfig(
    self,
    *,
    action: Optional[RuleAction] = None,
    conditions: Optional[List[RuleCondition]] = None
)
```

Conditions and action if conditions are met


The values for the conditions are taken from the collector.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`action`|**Optional\[[RuleAction](toloka.client.actions.RuleAction.md)\]**|<p>Action if conditions are met (for example, close access to the project).</p>
`conditions`|**Optional\[List\[[RuleCondition](toloka.client.conditions.RuleCondition.md)\]\]**|<p>Conditions (for example, skipping 10 sets of tasks in a row).</p>
