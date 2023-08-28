# TaskSuiteCreateRequestParameters
`toloka.client.task_suite.TaskSuiteCreateRequestParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/task_suite.py#L78)

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

Parameters for creating a task suite.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**Optional\[UUID\]**|<p>The UUID of the operation that conforms to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). The UUID is used if `async_mode` is `True`.</p> <p>Specify UUID to avoid accidental errors like Toloka operation duplication caused by network problems. If you send several requests with the same `operation_id`, Toloka performs the operation only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p>Default value: `True`.</p>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>`True` — Use the overlap that is set in the `defaults.default_overlap_for_new_task_suites` pool parameter.</li> <li>`False` — Use the overlap that is set in the `overlap` task suite parameter.</li> </ul> <p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed.</p>
