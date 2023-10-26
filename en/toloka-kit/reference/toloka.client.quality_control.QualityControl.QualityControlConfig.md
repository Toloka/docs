# QualityControlConfig
`toloka.client.quality_control.QualityControl.QualityControlConfig` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/quality_control.py#L110)

```python
QualityControlConfig(
    self,
    *,
    rules: Optional[List[RuleConfig]] = None,
    collector_config: Optional[CollectorConfig] = None
)
```

A quality control rules configuration.


A rule consists of conditions, and an action to perform when the conditions are met. The rule conditions use statistics provided by a connected collector.

An example of the configuration.
Toloka collects statistics of skipped tasks. If 10 task suites are skipped in a row, then a Toloker can no longer access a project.

To learn more, see:
* [Quality control rules](https://toloka.ai/docs/api/quality_control/) in the API.
* [Quality control rules](https://toloka.ai/docs/guide/control/) in the guide.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`rules`|**Optional\[List\[[RuleConfig](toloka.client.quality_control.QualityControl.QualityControlConfig.RuleConfig.md)\]\]**|<p>The conditions and the action.</p>
`collector_config`|**Optional\[[CollectorConfig](toloka.client.collectors.CollectorConfig.md)\]**|<p>The configuration of the collector.</p>
