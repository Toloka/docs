# create_tasks_async
`toloka.client.TolokaClient.create_tasks_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L2484)

Creates tasks in Toloka asynchronously.


You can send a maximum of 100,000 requests of this kind per minute and a maximum of 2,000,000 requests per day.

See also the [create_tasks](toloka.client.TolokaClient.create_tasks.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`tasks`|**List\[[Task](toloka.client.task.Task.md)\]**|<p>A list of tasks to be created.</p>
`operation_id`|**Optional\[UUID\]**|<p>The UUID of the operation that conforms to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). The UUID is used if `async_mode` is `True`.</p> <p>Specify UUID to avoid accidental errors like Toloka operation duplication caused by network problems. If you send several requests with the same `operation_id`, Toloka performs the operation only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p>Default value: `True`.</p>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>`True` — Use the overlap that is set in the `defaults.default_overlap_for_new_tasks` pool parameter.</li> <li>`False` — Use the overlap that is set in the `overlap` task parameter.</li> </ul> <p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed. </p><p>Default value: `False`.</p>
`skip_invalid_items`|**Optional\[bool\]**|<p>Task validation option:</p> <ul> <li>`True` — All valid tasks are added. If a task does not pass validation, then it is not added to Toloka. All such tasks are listed in the response.</li> <li>`False` — If any task does not pass validation, then the operation is cancelled and no tasks are added to Toloka.</li> </ul> <p>Default value: `False`.</p>

* **Returns:**

  An object to track the progress of the operation.

* **Return type:**

  [TasksCreateOperation](toloka.client.operations.TasksCreateOperation.md)

**Examples:**


```python
tasks = [
    toloka.client.Task(input_values={'image': 'https://some.url/img0.png'}, pool_id='1080020'),
    toloka.client.Task(input_values={'image': 'https://some.url/img1.png'}, pool_id='1080020')
]
tasks_op = toloka_client.create_tasks_async(tasks)
toloka_client.wait_operation(tasks_op)
```
