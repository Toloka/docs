# create_tasks
`toloka.async_client.client.AsyncTolokaClient.create_tasks` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L0)

Creates several tasks in Toloka.


You can create general and control tasks together. Tasks can be added to different pools.
Note that pools must be configured before accepting new tasks. For example, [mixer configuration](toloka.client.pool.mixer_config.MixerConfig.md) must be set.

If `async_mode` is `True`, `create_tasks` starts asynchronous operation internally and waits for the completion of it.
It is recommended to create no more than 10,000 tasks per request in this mode.

If `async_mode` is `False`, no more than 5000 tasks can be created in a single request.
Do not change `async_mode` to `False`, if you don't understand clearly why you need it.

You can send no more than 100,000 requests per minute and no more than 2,000,000 requests per day.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`tasks`|**List\[[Task](toloka.client.task.Task.md)\]**|<p>A list of tasks to be created.</p>
`operation_id`|**Optional\[UUID\]**|<p>The UUID of the operation that conforms to the [RFC4122 standard](https://tools.ietf.org/html/rfc4122). The UUID is used if `async_mode` is `True`.</p> <p>Specify UUID to avoid accidental errors like Toloka operation duplication caused by network problems. If you send several requests with the same `operation_id`, Toloka performs the operation only once.</p>
`async_mode`|**Optional\[bool\]**|<p>Request processing mode:</p> <ul> <li>`True` — Asynchronous operation is started internally.</li> <li>`False` — The request is processed synchronously.</li> </ul> <p></p><p>Default value: `True`.</p>
`allow_defaults`|**Optional\[bool\]**|<p>Active overlap setting:</p> <ul> <li>`True` — Use the overlap that is set in the `defaults.default_overlap_for_new_tasks` pool parameter.</li> <li>`False` — Use the overlap that is set in the `overlap` task parameter.</li> </ul> <p></p><p>Default value: `False`.</p>
`open_pool`|**Optional\[bool\]**|<p>Open the pool immediately after creating a task suite, if the pool is closed. </p><p>Default value: `False`.</p>
`skip_invalid_items`|**Optional\[bool\]**|<p>Task validation option:</p> <ul> <li>`True` — All valid tasks are added. If a task does not pass validation, then it is not added to Toloka. All such tasks are listed in the response.</li> <li>`False` — If any task does not pass validation, then the operation is cancelled and no tasks are added to Toloka.</li> </ul> <p></p><p>Default value: `False`.</p>

* **Returns:**

  The result of the operation.

* **Return type:**

  [TaskBatchCreateResult](toloka.client.batch_create_results.TaskBatchCreateResult.md)

**Examples:**

The first example shows how to create tasks using a TSV file.

```python
import pandas
dataset = pandas.read_csv('dataset.tsv', sep=';')
tasks = [
    toloka.client.Task(input_values={'image': url}, pool_id='1080020')
    for url in dataset['image'].values[:50]
]
result = toloka_client.create_tasks(tasks, allow_defaults=True)
print(len(result.items))
```

The second example shows how to add control tasks.

```python
import pandas
dataset = pandas.read_csv('labeled_dataset.tsv', sep=';')
golden_tasks = []
for _, row in dataset.iterrows():
    golden_tasks.append(
        toloka.client.Task(
            input_values={'image': row['image']},
            known_solutions=[
                toloka.client.BaseTask.KnownSolution(output_values={'animal': row['label']})
            ],
            pool_id='1080020',
        )
    )
result = toloka_client.create_tasks(golden_tasks, allow_defaults=True)
print(len(result.items))
```
