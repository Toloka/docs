# TaskSuitesCreateRequestParameters
`toloka.client.task_suite.TaskSuitesCreateRequestParameters` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/task_suite.py#L94)

```python
TaskSuitesCreateRequestParameters(
    self,
    *,
    operation_id: Optional[UUID] = ...,
    async_mode: Optional[bool] = True,
    allow_defaults: Optional[bool] = None,
    open_pool: Optional[bool] = None,
    skip_invalid_items: Optional[bool] = None
)
```

Parameters for creating task suites.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**Optional\[UUID\]**|<p>The ID of the operation conforming to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). We recommended sending the operation ID in the `POST` requests to avoid accidental errors: when you send several requests with the same `operation_id`, the operation will be performed only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously. A maximum of 5000 task suites can be added in a single request in this mode. </p><p>Default value: `True`.</li> </ul>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>`True` — Use the overlap that is set in the `defaults.default_overlap_for_new_task_suites` pool parameter.</li> <li>`False` — Use the overlap that is set in the `overlap` task suite parameter.</li> </ul> <p></p><p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed.</p>
`skip_invalid_items`|**Optional\[bool\]**|<p>Task suite validation option:</p> <ul> <li>`True` — All valid task suites are added. If a task suite does not pass validation, then it is not added to Toloka.</li> <li>`False` — If any task suite does not pass validation, then operation is cancelled and no task suites are added to Toloka.</li> </ul> <p></p><p>Default value: `False`.</p>
