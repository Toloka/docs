# TaskOverlapPatch
`toloka.client.task.TaskOverlapPatch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/task.py#L154)

```python
TaskOverlapPatch(
    self,
    *,
    overlap: Optional[int] = None,
    infinite_overlap: Optional[bool] = None
)
```

Parameters for changing the overlap of a specific Task

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`overlap`|**Optional\[int\]**|<p>Overlap value.</p>
`infinite_overlap`|**Optional\[bool\]**|<p>Infinite overlap:</p> <ul> <li>True — Assign the task to all Tolokers. It is useful for training and control tasks.</li> <li>False — Overlap value specified for the task or for the pool is used. </p><p>Default value: False.</li> </ul>
