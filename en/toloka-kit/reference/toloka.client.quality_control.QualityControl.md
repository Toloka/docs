# QualityControl
`toloka.client.quality_control.QualityControl` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/quality_control.py#L26)

```python
QualityControl(
    self,
    *,
    training_requirement: Optional[TrainingRequirement] = None,
    captcha_frequency: Union[CaptchaFrequency, str, None] = None,
    configs: Optional[List[QualityControlConfig]] = ...,
    checkpoints_config: Optional[CheckpointsConfig] = None
)
```

Quality control settings.


Quality control lets you get more accurate responses, restrict access to tasks for Tolokers who give responses of low quality, and filter out robots.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`configs`|**Optional\[List\[[QualityControlConfig](toloka.client.quality_control.QualityControl.QualityControlConfig.md)\]\]**|<p>A list of quality control rules configurations.</p>
`checkpoints_config`|**Optional\[[CheckpointsConfig](toloka.client.quality_control.QualityControl.CheckpointsConfig.md)\]**|<p>A selective majority vote check configuration.</p>
`training_requirement`|**Optional\[[TrainingRequirement](toloka.client.quality_control.QualityControl.TrainingRequirement.md)\]**|<p>Parameters for linking a training pool to a general task pool.</p>
`captcha_frequency`|**Optional\[[CaptchaFrequency](toloka.client.quality_control.QualityControl.CaptchaFrequency.md)\]**|<p>**Deprecated.** A frequency of showing captchas.</p> <ul> <li>`LOW` — Show one for every 20 tasks.</li> <li>`MEDIUM`, `HIGH` — Show one for every 10 tasks.</li> </ul> <p>By default, captchas aren't displayed.</p>

**Examples:**

A quality control rule that restricts access if a Toloker responds too fast.

```python
new_pool = toloka.client.pool.Pool()
new_pool.quality_control.add_action(
    collector=toloka.client.collectors.AssignmentSubmitTime(history_size=5, fast_submit_threshold_seconds=20),
    conditions=[toloka.client.conditions.FastSubmittedCount > 1],
    action=toloka.client.actions.RestrictionV2(
        scope=toloka.client.user_restriction.UserRestriction.ALL_PROJECTS,
        duration=10,
        duration_unit='DAYS',
        private_comment='Fast responses',
    )
)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[add_action](toloka.client.quality_control.QualityControl.add_action.md)| Adds a quality control rule configuration.
