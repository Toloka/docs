# TrainingRequirement
`toloka.client.quality_control.QualityControl.TrainingRequirement` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/quality_control.py#L58)

```python
TrainingRequirement(
    self,
    *,
    training_pool_id: Optional[str] = None,
    training_passing_skill_value: Optional[int] = None
)
```

Parameters for linking a training pool to a general task pool.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`training_pool_id`|**Optional\[str\]**|<p>The ID of the training pool.</p>
`training_passing_skill_value`|**Optional\[int\]**|<p>The percentage of correct answers in training tasks required in order to access the general tasks. Only the first answer of the Toloker in each task is taken into account.</p> <p>Allowed values: from 0 to 100.</p>
