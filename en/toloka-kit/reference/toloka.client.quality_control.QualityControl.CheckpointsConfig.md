# CheckpointsConfig
`toloka.client.quality_control.QualityControl.CheckpointsConfig` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/quality_control.py#L78)

```python
CheckpointsConfig(
    self,
    *,
    real_settings: Optional[Settings] = None,
    golden_settings: Optional[Settings] = None,
    training_settings: Optional[Settings] = None
)
```

A selective majority vote check configuration.


This quality control method checks some of Toloker's responses against the majority of Tolokers. To do this, it changes the overlap of those tasks.

An example of the configuration:
    * For the first 100 tasks completed by a Toloker in the pool, every 5th task is checked. The overlap of these tasks is increased to 5.
    * After completing 100 tasks, every 25th task is checked.

Learn more about the [Selective majority vote check](https://toloka.ai/docs/guide/selective-mvote/).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`real_settings`|**Optional\[[Settings](toloka.client.quality_control.QualityControl.CheckpointsConfig.Settings.md)\]**|<p>Selective majority vote settings for general tasks.</p>
`golden_settings`|**Optional\[[Settings](toloka.client.quality_control.QualityControl.CheckpointsConfig.Settings.md)\]**|<p>Selective majority vote settings for control tasks.</p>
`training_settings`|**Optional\[[Settings](toloka.client.quality_control.QualityControl.CheckpointsConfig.Settings.md)\]**|<p>Selective majority vote settings for training tasks.</p>
