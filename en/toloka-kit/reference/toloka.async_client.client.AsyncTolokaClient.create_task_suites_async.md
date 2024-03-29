# create_task_suites_async
`toloka.async_client.client.AsyncTolokaClient.create_task_suites_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L0)

Creates several task suites in Toloka asynchronously.


You can send a maximum of 100,000 requests of this kind per minute and 2,000,000 requests per day.
It is recommended that you create no more than 10,000 task suites in a single request.

See also the [create_task_suites](toloka.client.TolokaClient.create_task_suites.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_suites`|**List\[[TaskSuite](toloka.client.task_suite.TaskSuite.md)\]**|<p>A list of task suites to be created.</p>
`operation_id`|**Optional\[UUID\]**|<p>The UUID of the operation that conforms to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). The UUID is used if `async_mode` is `True`.</p> <p>Specify UUID to avoid accidental errors like Toloka operation duplication caused by network problems. If you send several requests with the same `operation_id`, Toloka performs the operation only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p>Default value: `True`.</p>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>`True` — Use the overlap that is set in the `defaults.default_overlap_for_new_task_suites` pool parameter.</li> <li>`False` — Use the overlap that is set in the `overlap` task suite parameter.</li> </ul> <p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed.</p>
`skip_invalid_items`|**Optional\[bool\]**|<p>Task suite validation option:</p> <ul> <li>`True` — All valid task suites are added. If a task suite doesn't pass validation, then it is not added to Toloka.</li> <li>`False` — If any task suite doesn't pass validation, then operation is cancelled and no task suites are added to Toloka.</li> </ul> <p>Default value: `False`.</p>

* **Returns:**

  An object to track the progress of the operation.

* **Return type:**

  [TaskSuiteCreateBatchOperation](toloka.client.operations.TaskSuiteCreateBatchOperation.md)

**Examples:**


```python
task_suites = [
    toloka.client.TaskSuite(
        pool_id='1086170',
        overlap=1,
        tasks=[
            toloka.client.Task(input_values={
                'question': 'Choose a random country'
            })
        ]
    )
]
task_suites_op = toloka_client.create_task_suites_async(task_suites)
toloka_client.wait_operation(task_suites_op)
```
