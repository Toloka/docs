# create_task_suites_async
`toloka.async_client.client.AsyncTolokaClient.create_task_suites_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L0)

Creates several task suites in Toloka asynchronously.


You can send a maximum of 100,000 requests of this kind per minute and 2,000,000 requests per day.
It is recommended that you create no more than 10,000 task suites in a single request.

See also the [create_task_suites](toloka.client.TolokaClient.create_task_suites.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_suites`|**List\[[TaskSuite](toloka.client.task_suite.TaskSuite.md)\]**|<p>A list of task suites to be created.</p>
`operation_id`|**Optional\[UUID\]**|<p>The ID of the operation conforming to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). Use it if the `async_mode` is set to `True`.</p>
`skip_invalid_items`|**Optional\[bool\]**|<p>Task suite validation option:</p> <ul> <li>True — All valid task suites are added. If a task suite does not pass validation, then it is not added to Toloka.</li> <li>False — If any task suite does not pass validation, then operation is cancelled and no task suites are added to Toloka.</li> </ul> <p></p><p>Default value: `False`.</p>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>True — Use the overlap that is set in the `defaults.default_overlap_for_new_task_suites` pool parameter.</li> <li>False — Use the overlap that is set in the `overlap` task suite parameter.</li> </ul> <p></p><p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>True — Asynchronous operation is started internally.</li> <li>False — The request is processed synchronously. A maximum of 5000 task suites can be added in a single request in this mode.</li> </ul> <p></p><p>Default value: `True`.</p>

* **Returns:**

  An object to track the progress of the operation.

* **Return type:**

  [TaskSuiteCreateBatchOperation](toloka.client.operations.TaskSuiteCreateBatchOperation.md)

**Examples:**


```python
task_suites = [
    toloka.client.TaskSuite(
        pool_id='1',
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
