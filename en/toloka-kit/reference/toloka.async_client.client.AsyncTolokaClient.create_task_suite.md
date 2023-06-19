# create_task_suite
`toloka.async_client.client.AsyncTolokaClient.create_task_suite` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L0)

Creates a task suite in Toloka.


Usually, you don't need to create a task suite manually, because Toloka can group tasks into suites automatically.

Use this method if you need to group specific tasks together or to set different parameters in different task suites.

You can send a maximum of 100,000 requests of this kind per minute and 2,000,000 requests per day.
To create several task suites at once use the [create_task_suites](toloka.client.TolokaClient.create_task_suites.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_suite`|**[TaskSuite](toloka.client.task_suite.TaskSuite.md)**|<p>A task suite to be created.</p>
`operation_id`|**Optional\[UUID\]**|<p>The ID of the operation conforming to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). We recommended sending the operation ID in the `POST` requests to avoid accidental errors: when you send several requests with the same `operation_id`, the operation will be performed only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p></p><p>Default value: `True`.</p>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>`True` — Use the overlap that is set in the `defaults.default_overlap_for_new_task_suites` pool parameter.</li> <li>`False` — Use the overlap that is set in the `overlap` task suite parameter.</li> </ul> <p></p><p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed.</p>

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
