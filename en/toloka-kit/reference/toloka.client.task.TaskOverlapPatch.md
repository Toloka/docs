# TaskOverlapPatch
`toloka.client.task.TaskOverlapPatch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/task.py#L160)

```python
TaskOverlapPatch(
    self,
    *,
    overlap: Optional[int] = None,
    infinite_overlap: Optional[bool] = None
)
```

Parameters for changing the overlap of a task.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`overlap`|**Optional\[int\]**|<p>The new overlap value.</p>
`infinite_overlap`|**Optional\[bool\]**|<ul> <li>True — The task is assigned to all Tolokers. It is usually set for training and control tasks.</li> <li>False — An overlap value specified for the task or for the pool is used.</li> </ul> <p></p><p>Default value: `False`.</p>
