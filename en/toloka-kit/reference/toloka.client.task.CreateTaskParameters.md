# CreateTaskParameters
`toloka.client.task.CreateTaskParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/task.py#L106)

```python
CreateTaskParameters(
    self,
    *,
    allow_defaults: Optional[bool] = None,
    open_pool: Optional[bool] = None,
    operation_id: Optional[UUID] = ...
)
```

Parameters used with the [create_task](toloka.client.TolokaClient.create_task.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>`True` — Use the overlap that is set in the `defaults.default_overlap_for_new_tasks` pool parameter.</li> <li>`False` — Use the overlap that is set in the `overlap` task parameter.</li> </ul> <p></p><p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed. </p><p>Default value: `False`.</p>
