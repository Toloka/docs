# find_tasks
`toloka.client.TolokaClient.find_tasks` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/__init__.py#L2353)

Finds tasks that match certain criteria.


The number of returned tasks is limited. To find remaining tasks call `find_tasks` with updated search criteria.

To iterate over all matching tasks you may use the [get_tasks](toloka.client.TolokaClient.get_tasks.md) method.

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
`sort`|**Union\[List\[str\], [TaskSortItems](toloka.client.search_requests.TaskSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned tasks limit. The default limit is 50. The maximum allowed limit is 100,000.</p>

* **Returns:**

  Found tasks and a flag showing whether there are more matching tasks exceeding the limit.

* **Return type:**

  [TaskSearchResult](toloka.client.search_results.TaskSearchResult.md)

**Examples:**

To find three most recently created tasks in a pool, call the method with the following parameters:

```python
toloka_client.find_tasks(pool_id='1', sort=['-created', '-id'], limit=3)
```
