# create_task_suites_async
`toloka.client.TolokaClient.create_task_suites_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/__init__.py#L2451)

Creates many task suites in pools, asynchronous version


You can send a maximum of 100,000 requests of this kind per minute and 2,000,000 requests per day.
Recommended maximum of 10,000 task suites per request.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_suites`|**List\[[TaskSuite](toloka.client.task_suite.TaskSuite.md)\]**|<p>List of task suites, that will be created.</p>
`operation_id`|**Optional\[UUID\]**|<p>Operation ID for asynchronous loading of task suites.</p>
`skip_invalid_items`|**Optional\[bool\]**|<p>Validation parameters:</p> <ul> <li>True - Create the task suites that passed validation. Skip the rest of the task suites.</li> <li>False - If at least one of the task suites didn&#x27;t pass validation, stop the operation and   don&#x27;t create the task suites.</li> </ul>
`allow_defaults`|**Optional\[bool\]**|<p>Overlap settings:</p> <ul> <li>True - Use the overlap that is set in the pool parameters.</li> <li>False - Use the overlap that is set in the task suite parameters (in the `overlap` field).</li> </ul>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed.</p>
`async_mode`|**Optional\[bool\]**|<p>How the request is processed:</p> <ul> <li>True — deferred. The query results in an asynchronous operation running in the background.   Answer contains information about the operation (start and end time, status, number of sets).</li> <li>False — synchronous. Answer contains information about the generated sets of tasks.   You can send a maximum of 5000 task sets in a single request.</li> </ul>

* **Returns:**

  An operation upon completion of which you can get the created task suites.

* **Return type:**

  [TaskSuiteCreateBatchOperation](toloka.client.operations.TaskSuiteCreateBatchOperation.md)

**Examples:**


```python
task_suites = [
    toloka.task_suite.TaskSuite(
        pool_id=pool.id,
        overlap=1,
        tasks=[
            toloka.task.Task(input_values={
                'input1': some_input_value,
                'input2': some_input_value
            })
        ]
    )
]
task_suites_op = toloka_client.create_task_suites_async(task_suites)
toloka_client.wait_operation(task_suites_op)
```
