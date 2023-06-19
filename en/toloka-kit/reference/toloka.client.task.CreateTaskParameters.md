# CreateTaskParameters
`toloka.client.task.CreateTaskParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/task.py#L103)

```python
CreateTaskParameters(
    self,
    *,
    operation_id: Optional[UUID] = ...,
    async_mode: Optional[bool] = True,
    allow_defaults: Optional[bool] = None,
    open_pool: Optional[bool] = None
)
```

Parameters used with the [create_task](toloka.client.TolokaClient.create_task.md) method.


If the operation is started in an asynchronous mode,
we recommend that you send the `operation_id` to avoid creating the same tasks multiple times. You can use this ID later to get information about the operation.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**Optional\[UUID\]**|<p>The ID of the operation conforming to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). We recommended sending the operation ID in the `POST` requests to avoid accidental errors: when you send several requests with the same `operation_id`, the operation will be performed only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally and `create_tasks` waits for the completion of it. It is recommended to create no more than 10,000 tasks per request in this mode.</li> <li>`False` — The request is processed synchronously. A maximum of 5000 tasks can be added in a single request in this mode. </p><p>Default value: `True`.</li> </ul>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>`True` — Use the overlap that is set in the `defaults.default_overlap_for_new_tasks` pool parameter.</li> <li>`False` — Use the overlap that is set in the `overlap` task parameter.</li> </ul> <p></p><p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed. </p><p>Default value: `False`.</p>
