# create_task_suite
`toloka.async_client.client.AsyncTolokaClient.create_task_suite` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L0)

Creates a task suite in Toloka.


Usually, you don't need to create a task suite manually, because Toloka can group tasks into suites automatically.

Use this method if you need to group specific tasks together or to set different parameters in different task suites.

You can send a maximum of 100,000 requests of this kind per minute and 2,000,000 requests per day.
To create several task suites at once use the [create_task_suites](toloka.client.TolokaClient.create_task_suites.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_suite`|**[TaskSuite](toloka.client.task_suite.TaskSuite.md)**|<p>A task suite to be created.</p>
`operation_id`|**Optional\[UUID\]**|<p>The ID of the operation conforming to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). Use it if the `async_mode` is set to `True`.</p>
`skip_invalid_items`|**Optional\[bool\]**|<p>Task suite validation option:</p> <ul> <li>True — All valid task suites are added. If a task suite does not pass validation, then it is not added to Toloka.</li> <li>False — If any task suite does not pass validation, then operation is cancelled and no task suites are added to Toloka.</li> </ul> <p></p><p>Default value: `False`.</p>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>True — Use the overlap that is set in the `defaults.default_overlap_for_new_task_suites` pool parameter.</li> <li>False — Use the overlap that is set in the `overlap` task suite parameter.</li> </ul> <p></p><p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>True — Asynchronous operation is started internally.</li> <li>False — The request is processed synchronously. A maximum of 5000 task suites can be added in a single request in this mode.</li> </ul> <p></p><p>Default value: `True`.</p>

* **Returns:**

  Created task suite.

* **Return type:**

  [TaskSuite](toloka.client.task_suite.TaskSuite.md)

**Examples:**


```python
new_task_suite = toloka.client.TaskSuite(
    pool_id='1',
    tasks=[toloka.client.Task(input_values={'label': 'Cats vs Dogs'})],
    overlap=2
)
toloka_client.create_task_suite(new_task_suite)
```
