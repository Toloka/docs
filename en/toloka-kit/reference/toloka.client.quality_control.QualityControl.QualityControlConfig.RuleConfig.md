# RuleConfig
`toloka.client.quality_control.QualityControl.QualityControlConfig.RuleConfig` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/quality_control.py#L127)

```python
RuleConfig(
    self,
    *,
    action: Optional[RuleAction] = None,
    conditions: Optional[List[RuleCondition]] = None
)
```

Rule conditions and an action.


The action is performed if conditions are met. Multiple conditions are combined with the AND operator.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`action`|**Optional\[[RuleAction](toloka.client.actions.RuleAction.md)\]**|<p>The action.</p>
`conditions`|**Optional\[List\[[RuleCondition](toloka.client.conditions.RuleCondition.md)\]\]**|<p>A list of conditions.</p>
