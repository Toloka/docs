# find_task_suites
`toloka.async_client.client.AsyncTolokaClient.find_task_suites` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L0)

Finds task suites that match certain criteria.


The number of returned task suites is limited. To find remaining task suites call `find_task_suites` with updated search criteria.

To iterate over all matching task suites you may use the [get_task_suites](toloka.client.TolokaClient.get_task_suites.md) method.

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
`sort`|**Union\[List\[str\], [TaskSuiteSortItems](toloka.client.search_requests.TaskSuiteSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned task suites limit. The maximum allowed value: 100,000. The default value: 50.</p>

* **Returns:**

  Found task suites and a flag showing whether there are more matching task suites exceeding the limit.

* **Return type:**

  [TaskSuiteSearchResult](toloka.client.search_results.TaskSuiteSearchResult.md)

**Examples:**

Find three most recently created task suites in a specified pool.

```python
find_result = toloka_client.find_task_suites(pool_id='1086170', sort=['-created', '-id'], limit=3)
task_suites = find_result.items
```
