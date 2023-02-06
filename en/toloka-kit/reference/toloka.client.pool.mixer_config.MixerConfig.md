# MixerConfig
`toloka.client.pool.mixer_config.MixerConfig` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/pool/mixer_config.py#L7)

```python
MixerConfig(
    self,
    *,
    real_tasks_count: int = 0,
    golden_tasks_count: int = 0,
    training_tasks_count: int = 0,
    min_real_tasks_count: Optional[int] = None,
    min_golden_tasks_count: Optional[int] = None,
    min_training_tasks_count: Optional[int] = None,
    force_last_assignment: Optional[bool] = None,
    force_last_assignment_delay_seconds: Optional[int] = None,
    mix_tasks_in_creation_order: Optional[bool] = None,
    shuffle_tasks_in_task_suite: Optional[bool] = None,
    golden_task_distribution_function: Optional[TaskDistributionFunction] = None,
    training_task_distribution_function: Optional[TaskDistributionFunction] = None
)
```

Settings for automatically grouping tasks into suites (smart mixing).


You can set the number of general, training and control tasks in a task suite. Also, you control task shuffling and other settings.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`real_tasks_count`|**int**|<p>The number of general tasks in a task suite. If `training_task_distribution_function` or `golden_task_distribution_function` are used then `real_tasks_count` denotes the maximum number of tasks in a task suite.</p>
`golden_tasks_count`|**int**|<p>The number of control tasks in a task suite.</p>
`training_tasks_count`|**int**|<p>The number of training tasks in a task suite.</p>
`min_real_tasks_count`|**Optional\[int\]**|<p>The minimum number of general tasks in a task suite if there are not enough tasks left to create a full task suite. Allowed range: from 0 to `real_tasks_count`. By default, the `min_real_tasks_count` value equals to the `real_tasks_count` value.</p>
`min_golden_tasks_count`|**Optional\[int\]**|<p>The minimum number of control tasks in a task suite if there are not enough control tasks left to create a full task suite. Allowed range: from 0 to `golden_tasks_count`. By default, the `min_golden_tasks_count` value equals to the `golden_tasks_count` value.</p>
`min_training_tasks_count`|**Optional\[int\]**|<p>The minimum number of training tasks in a task suite if there are not enough training tasks left to create a full task suite. Allowed range: from 0 to `training_tasks_count`. By default, the `min_training_tasks_count` value equals to the `training_tasks_count` value.</p>
`force_last_assignment`|**Optional\[bool\]**|<p>A setting used when the number of remaining general tasks in the pool is less than the `min_real_tasks_count` value. Note, that there must be enough control and training tasks to create a task suite.</p> <ul> <li>`True` — An incomplete task suite is assigned.</li> <li>`False` — An incomplete task suite is not assigned. It is useful if you add tasks to an open pool.</li> </ul> <p>Default: `True`.</p>
`force_last_assignment_delay_seconds`|**Optional\[int\]**|<p>Time in seconds before assigning the last task suite. This parameter is used if `force_last_assignment` is set to `True`. Allowed range: from 0 to 86,400 seconds (one day).</p>
`mix_tasks_in_creation_order`|**Optional\[bool\]**|<ul> <li>`True` — Tasks are grouped in task suites in the order they were created.</li> <li>`False` — Tasks are chosen for a task suite in a random order.</li> </ul>
`shuffle_tasks_in_task_suite`|**Optional\[bool\]**|<ul> <li>`True` — Tasks in a task suite are shuffled on the page.</li> <li>`False` — Tasks in a task suite are placed on the page in the order they were created.</li> </ul>
`golden_task_distribution_function`|**Optional\[[TaskDistributionFunction](toloka.client.task_distribution_function.TaskDistributionFunction.md)\]**|<p>Customizing the number of control tasks in a task suite depending on completed tasks by a Toloker.</p>
`training_task_distribution_function`|**Optional\[[TaskDistributionFunction](toloka.client.task_distribution_function.TaskDistributionFunction.md)\]**|<p>Customizing the number of training tasks in a task suite depending on completed tasks by a Toloker.</p>
