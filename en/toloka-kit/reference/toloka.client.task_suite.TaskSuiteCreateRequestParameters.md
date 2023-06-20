# TaskSuiteCreateRequestParameters
`toloka.client.task_suite.TaskSuiteCreateRequestParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/task_suite.py#L78)

```python
TaskSuiteCreateRequestParameters(
    self,
    *,
    operation_id: Optional[UUID] = ...,
    async_mode: Optional[bool] = True,
    allow_defaults: Optional[bool] = None,
    open_pool: Optional[bool] = None
)
```

Parameters for creating task suite.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**Optional\[UUID\]**|<p>The ID of the operation conforming to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). We recommended sending the operation ID in the `POST` requests to avoid accidental errors: when you send several requests with the same `operation_id`, the operation will be performed only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p>Default value: `True`.</p>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>`True` — Use the overlap that is set in the `defaults.default_overlap_for_new_task_suites` pool parameter.</li> <li>`False` — Use the overlap that is set in the `overlap` task suite parameter.</li> </ul> <p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed.</p>
