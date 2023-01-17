# BaseTask
`toloka.client.task.BaseTask` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/task.py#L20)

```python
BaseTask(
    self,
    *,
    input_values: Optional[Dict[str, Any]] = None,
    known_solutions: Optional[List[KnownSolution]] = None,
    message_on_unknown_solution: Optional[str] = None,
    id: Optional[str] = None,
    origin_task_id: Optional[str] = None
)
```

A base class for tasks.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`input_values`|**Optional\[Dict\[str, Any\]\]**|<p>A dictionary with input data for a task. Input field names are keys in the dictionary.</p>
`known_solutions`|**Optional\[List\[[KnownSolution](toloka.client.task.BaseTask.KnownSolution.md)\]\]**|<p>A list of all responses considered correct. It is used with control and training tasks. If there are several output fields, then you must specify all their correct combinations.</p>
`message_on_unknown_solution`|**Optional\[str\]**|<p>A hint used in training tasks.</p>
`id`|**Optional\[str\]**|<p>The ID of a task.</p>
`origin_task_id`|**Optional\[str\]**|<p>The ID of a parent task. This parameter is set if the task was created by copying.</p>
