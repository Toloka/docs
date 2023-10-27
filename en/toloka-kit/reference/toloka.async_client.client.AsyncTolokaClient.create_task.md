# create_task
`toloka.async_client.client.AsyncTolokaClient.create_task` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L0)

Creates a new task in Toloka.


If `async_mode` is `True` then an asynchronous operation is started internally and `create_task` waits for the completion of it.

You can send a maximum of 100,000 requests of this kind per minute and a maximum of 2,000,000 requests per day.

To create several tasks at once use the [create_tasks](toloka.client.TolokaClient.create_tasks.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task`|**[Task](toloka.client.task.Task.md)**|<p>The task to be created.</p>
`operation_id`|**Optional\[UUID\]**|<p>The UUID of the operation that conforms to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). The UUID is used if `async_mode` is `True`.</p> <p>Specify UUID to avoid accidental errors like Toloka operation duplication caused by network problems. If you send several requests with the same `operation_id`, Toloka performs the operation only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p></p><p>Default value: `True`.</p>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>`True` — Use the overlap that is set in the `defaults.default_overlap_for_new_tasks` pool parameter.</li> <li>`False` — Use the overlap that is set in the `overlap` task parameter.</li> </ul> <p></p><p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed. </p><p>Default value: `False`.</p>

* **Returns:**

  The created task.

* **Return type:**

  [Task](toloka.client.task.Task.md)

**Examples:**


```python
task = toloka.client.Task(
    input_values={'image': 'https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/048e5760fc5a46faa434922b2447a527.jpg'},
    pool_id='1080020'
)
toloka_client.create_task(task=task, allow_defaults=True)
```
