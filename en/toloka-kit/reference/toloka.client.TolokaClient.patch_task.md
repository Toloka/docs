# patch_task
`toloka.client.TolokaClient.patch_task` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/__init__.py#L2315)

Changes a task overlap value.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_id`|**str**|<p>The ID of the task.</p>
`overlap`|**Optional\[int\]**|<p>Overlap value.</p>
`infinite_overlap`|**Optional\[bool\]**|<p>Infinite overlap:</p> <ul> <li>True — Assign the task to all Tolokers. It is useful for training and control tasks.</li> <li>False — Overlap value specified for the task or for the pool is used. </p><p>Default value: False.</li> </ul>
`baseline_solutions`|**Optional\[List\[[Task.BaselineSolution](toloka.client.task.Task.BaselineSolution.md)\]\]**|<p>Preliminary responses. This data simulates Tolokers&#x27; responses when calculating confidence in a response. It is used in dynamic overlap (also known as incremental relabeling or IRL) and aggregation of results by skill.</p>
`known_solutions`|**Optional\[List\[[BaseTask.KnownSolution](toloka.client.task.BaseTask.KnownSolution.md)\]\]**|<p>Responses and hints for control tasks and training tasks. If multiple output fields are included in the validation, all combinations of the correct response must be specified.</p>
`message_on_unknown_solution`|**Optional\[str\]**|<p>Hint for the task (for training tasks).</p>

* **Returns:**

  The task with updated fields.

* **Return type:**

  [Task](toloka.client.task.Task.md)
