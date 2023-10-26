# Settings
`toloka.client.quality_control.QualityControl.CheckpointsConfig.Settings` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/quality_control.py#L95)

```python
Settings(
    self,
    *,
    target_overlap: Optional[int] = None,
    task_distribution_function: Optional[TaskDistributionFunction] = None
)
```

Selective majority vote check settings.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`target_overlap`|**Optional\[int\]**|<p>The overlap value used for selected tasks that are checked.</p>
`task_distribution_function`|**Optional\[[TaskDistributionFunction](toloka.client.task_distribution_function.TaskDistributionFunction.md)\]**|<p>The configuration of selecting tasks.</p>
