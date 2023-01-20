# add_action
`toloka.client.quality_control.QualityControl.add_action` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/quality_control.py#L143)

```python
add_action(
    self,
    collector: CollectorConfig,
    action: RuleAction,
    conditions: List[RuleCondition]
)
```

Adds new QualityControlConfig to QualityControl object. Usually in pool.


See example in QualityControl class.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`collector`|**[CollectorConfig](toloka.client.collectors.CollectorConfig.md)**|<p>Parameters for collecting statistics (for example, the number of task skips in the pool).</p>
`action`|**[RuleAction](toloka.client.actions.RuleAction.md)**|<p>Action if conditions are met (for example, close access to the project).</p>
`conditions`|**List\[[RuleCondition](toloka.client.conditions.RuleCondition.md)\]**|<p>Conditions (for example, skipping 10 sets of tasks in a row).</p>
