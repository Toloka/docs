# TaskPatch
`toloka.client.task.TaskPatch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/task.py#L177)

```python
TaskPatch(
    self,
    *,
    overlap: Optional[int] = None,
    infinite_overlap: Optional[bool] = None,
    baseline_solutions: Optional[List[Task.BaselineSolution]] = None,
    known_solutions: Optional[List[BaseTask.KnownSolution]] = None,
    message_on_unknown_solution: Optional[str] = None
)
```

Parameters for changing a task.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`overlap`|**Optional\[int\]**|<p>The new overlap value.</p>
`infinite_overlap`|**Optional\[bool\]**|<ul> <li>`True` — The task is assigned to all Tolokers. It is usually set for training and control tasks.</li> <li>`False` — An overlap value specified for the task or for the pool is used.</li> </ul> <p></p><p>Default value: `False`.</p>
`baseline_solutions`|**Optional\[List\[[Task.BaselineSolution](toloka.client.task.Task.BaselineSolution.md)\]\]**|<p>Preliminary responses for dynamic overlap and aggregation of results by a skill. They are used to calculate a confidence level of the first responses from Tolokers.</p>
`known_solutions`|**Optional\[List\[[BaseTask.KnownSolution](toloka.client.task.BaseTask.KnownSolution.md)\]\]**|<p>A list of all responses considered correct. It is used with control and training tasks. If there are several output fields, then you must specify all their correct combinations.</p>
`message_on_unknown_solution`|**Optional\[str\]**|<p>A hint used in training tasks.</p>
