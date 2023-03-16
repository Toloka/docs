# get_tasks
`toloka.client.TolokaClient.get_tasks` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/__init__.py#L2399)

Finds all tasks that match certain criteria.


`get_tasks` returns a generator. You can iterate over all found tasks using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort tasks use the [find_tasks](toloka.client.TolokaClient.find_tasks.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**Optional\[str\]**|<p>The ID of the pool to get tasks from.</p>
`overlap`|**Optional\[int\]**|<p>Tasks with an overlap equal to the specified value.</p>
`id_lt`|**Optional\[str\]**|<p>Tasks with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Tasks with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Tasks with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Tasks with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Tasks created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Tasks created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Tasks created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Tasks created after or on the specified date.</p>
`overlap_lt`|**Optional\[int\]**|<p>Tasks with an overlap less than the specified value.</p>
`overlap_lte`|**Optional\[int\]**|<p>Tasks with an overlap less than or equal to the specified value.</p>
`overlap_gt`|**Optional\[int\]**|<p>Tasks with an overlap greater than the specified value.</p>
`overlap_gte`|**Optional\[int\]**|<p>Tasks with an overlap greater than or equal to the specified value.</p>
`batch_size`|**Optional\[int\]**|<p>Returned tasks limit for each request. The default batch_size is 50. The maximum allowed batch_size is 100,000.</p>

* **Yields:**

  The next matching task.

* **Yield type:**

  Generator\[[Task](toloka.client.task.Task.md), None, None\]

**Examples:**

Getting all tasks from a single pool.

```python
results_list = list(toloka_client.get_tasks(pool_id='1'))
```
