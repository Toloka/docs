# get_task_suites
`toloka.client.TolokaClient.get_task_suites` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L2863)

Finds all task suites that match certain criteria.


`get_task_suites` returns a generator. You can iterate over all found task suites using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort task suites use the [find_task_suites](toloka.client.TolokaClient.find_task_suites.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_id`|**Optional\[str\]**|<p>Task suite containing a task with the specified ID.</p>
`pool_id`|**Optional\[str\]**|<p>Task suites from a pool with the specified ID.</p>
`overlap`|**Optional\[int\]**|<p>Task suites with an overlap equal to the specified value.</p>
`id_lt`|**Optional\[str\]**|<p>Task suites with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Task suites with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Task suites with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Task suites with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Task suites created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Task suites created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Task suites created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Task suites created after or on the specified date.</p>
`overlap_lt`|**Optional\[int\]**|<p>Task suites with an overlap less than the specified value.</p>
`overlap_lte`|**Optional\[int\]**|<p>Task suites with an overlap less than or equal to the specified value.</p>
`overlap_gt`|**Optional\[int\]**|<p>Task suites with an overlap greater than the specified value.</p>
`overlap_gte`|**Optional\[int\]**|<p>Task suites with an overlap greater than or equal to the specified value.</p>
`batch_size`|**Optional\[int\]**|<p>A limit of items returned by each request to Toloka. The maximum allowed value: 100,000. The default value: 50.</p>

* **Yields:**

  The next matching task suite.

* **Yield type:**

  Generator\[[TaskSuite](toloka.client.task_suite.TaskSuite.md), None, None\]

**Examples:**


```python
task_suites = list(toloka_client.get_task_suites(pool_id='1086170'))
```
