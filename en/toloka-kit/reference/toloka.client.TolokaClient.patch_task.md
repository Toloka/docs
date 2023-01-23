# patch_task
`toloka.client.TolokaClient.patch_task` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/__init__.py#L2398)

Changes a task overlap value.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_id`|**str**|<p>The ID of the task.</p>
`overlap`|**Optional\[int\]**|<p>The new overlap value.</p>
`infinite_overlap`|**Optional\[bool\]**|<ul> <li>True — The task is assigned to all Tolokers. It is usually set for training and control tasks.</li> <li>False — An overlap value specified for the task or for the pool is used.</li> </ul> <p></p><p>Default value: `False`.</p>
`baseline_solutions`|**Optional\[List\[[Task.BaselineSolution](toloka.client.task.Task.BaselineSolution.md)\]\]**|<p>Preliminary responses for dynamic overlap and aggregation of results by a skill. They are used to calculate a confidence level of the first responses from Tolokers.</p>
`known_solutions`|**Optional\[List\[[BaseTask.KnownSolution](toloka.client.task.BaseTask.KnownSolution.md)\]\]**|<p>A list of all responses considered correct. It is used with control and training tasks. If there are several output fields, then you must specify all their correct combinations.</p>
`message_on_unknown_solution`|**Optional\[str\]**|<p>A hint used in training tasks.</p>

* **Returns:**

  The task with updated fields.

* **Return type:**

  [Task](toloka.client.task.Task.md)
