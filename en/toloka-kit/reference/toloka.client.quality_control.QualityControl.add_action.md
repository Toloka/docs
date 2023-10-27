# add_action
`toloka.client.quality_control.QualityControl.add_action` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/quality_control.py#L148)

```python
add_action(
    self,
    collector: CollectorConfig,
    action: RuleAction,
    conditions: List[RuleCondition]
)
```

Adds a quality control rule configuration.


See an example in the description of the [QualityControl](toloka.client.quality_control.QualityControl.md) class.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`collector`|**[CollectorConfig](toloka.client.collectors.CollectorConfig.md)**|<p>A collector that provides statistics.</p>
`conditions`|**List\[[RuleCondition](toloka.client.conditions.RuleCondition.md)\]**|<p>Conditions based on statistics.</p>
`action`|**[RuleAction](toloka.client.actions.RuleAction.md)**|<p>An action performed if all conditions are met.</p>
