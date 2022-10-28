# CreateTaskParameters
`toloka.client.task.CreateTaskParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/task.py#L113)

```python
CreateTaskParameters(
    self,
    *,
    allow_defaults: Optional[bool] = None,
    open_pool: Optional[bool] = None
)
```

Parameters for Task creation controlling


Used when creating one Task.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>True — Use the overlap that is set in the `defaults.default_overlap_for_new_task_suites` pool parameter.</li> <li>False — Use the overlap that is set in the task parameters (in the `overlap` field).</li> </ul>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed.</p>
