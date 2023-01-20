# CreateTaskAsyncParameters
`toloka.client.task.CreateTaskAsyncParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/task.py#L122)

```python
CreateTaskAsyncParameters(
    self,
    *,
    allow_defaults: Optional[bool] = None,
    open_pool: Optional[bool] = None,
    operation_id: Optional[UUID] = None
)
```

Parameters used with the [create_tasks_async](toloka.client.TolokaClient.create_tasks_async.md) method.


Send the `operation_id` to avoid creating the same tasks multiple times. You can use this ID later to get information about the operation.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>True — Use the overlap that is set in the `defaults.default_overlap_for_new_tasks` pool parameter.</li> <li>False — Use the overlap that is set in the `overlap` task parameter.</li> </ul> <p></p><p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed. </p><p>Default value: `False`.</p>
`operation_id`|**Optional\[UUID\]**|<p>The ID of the operation conforming to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122).</p>
