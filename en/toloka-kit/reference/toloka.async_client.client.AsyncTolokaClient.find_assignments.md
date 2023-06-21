# find_assignments
`toloka.async_client.client.AsyncTolokaClient.find_assignments` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/__init__.py#L0)

Finds assignments that match certain criteria.


The number of returned assignments is limited. To find remaining assignments call `find_assignments` with updated search criteria.

To iterate over all matching assignments you may use the [get_assignments](toloka.client.TolokaClient.get_assignments.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`status`|**Union\[str, [Assignment.Status](toloka.client.assignment.Assignment.Status.md), List\[Union\[str, [Assignment.Status](toloka.client.assignment.Assignment.Status.md)\]\], None\]**|<p>Assignment status or a list of statuses. Refer to the [Assignment.Status](toloka.client.assignment.Assignment.Status.md) page for more information on the available `status` values.</p>
`task_id`|**Optional\[str\]**|<p>Assignments containing the task with the specified ID.</p>
`task_suite_id`|**Optional\[str\]**|<p>Assignments for a task suite with the specified ID.</p>
`pool_id`|**Optional\[str\]**|<p>Assignments in a pool with the specified ID.</p>
`user_id`|**Optional\[str\]**|<p>Assignments from a Toloker with the specified ID.</p>
`id_lt`|**Optional\[str\]**|<p>Assignments with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Assignments with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Assignments with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Assignments with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Task suites assigned before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Task suites assigned before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Task suites assigned after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Task suites assigned after or on the specified date.</p>
`submitted_lt`|**Optional\[datetime\]**|<p>Assignments completed before the specified date.</p>
`submitted_lte`|**Optional\[datetime\]**|<p>Assignments completed before or on the specified date.</p>
`submitted_gt`|**Optional\[datetime\]**|<p>Assignments completed after the specified date.</p>
`submitted_gte`|**Optional\[datetime\]**|<p>Assignments completed after or on the specified date.</p>
`accepted_lt`|**Optional\[datetime\]**|<p>Assignments accepted before the specified date.</p>
`accepted_lte`|**Optional\[datetime\]**|<p>Assignments accepted before or on the specified date.</p>
`accepted_gt`|**Optional\[datetime\]**|<p>Assignments accepted after the specified date.</p>
`accepted_gte`|**Optional\[datetime\]**|<p>Assignments accepted after or on the specified date.</p>
`rejected_lt`|**Optional\[datetime\]**|<p>Assignments rejected before the specified date.</p>
`rejected_lte`|**Optional\[datetime\]**|<p>Assignments rejected before or on the specified date.</p>
`rejected_gt`|**Optional\[datetime\]**|<p>Assignments rejected after the specified date.</p>
`rejected_gte`|**Optional\[datetime\]**|<p>Assignments rejected after or on the specified date.</p>
`skipped_lt`|**Optional\[datetime\]**|<p>Assigned task suites skipped before the specified date.</p>
`skipped_lte`|**Optional\[datetime\]**|<p>Assigned task suites skipped before or on the specified date.</p>
`skipped_gt`|**Optional\[datetime\]**|<p>Assigned task suites skipped after the specified date.</p>
`skipped_gte`|**Optional\[datetime\]**|<p>Assigned task suites skipped after or on the specified date.</p>
`expired_lt`|**Optional\[datetime\]**|<p>Assigned task suites expired before the specified date.</p>
`expired_lte`|**Optional\[datetime\]**|<p>Assigned task suites expired before or on the specified date.</p>
`expired_gt`|**Optional\[datetime\]**|<p>Assigned task suites expired after the specified date.</p>
`expired_gte`|**Optional\[datetime\]**|<p>Assigned task suites expired after or on the specified date.</p>
`sort`|**Union\[List\[str\], [AssignmentSortItems](toloka.client.search_requests.AssignmentSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned assignments limit. The default limit is 50. The maximum allowed limit is 100,000.</p>

* **Returns:**

  Found assignments and a flag showing whether there are more matching assignments.

* **Return type:**

  [AssignmentSearchResult](toloka.client.search_results.AssignmentSearchResult.md)

**Examples:**

Search for `SKIPPED` or `EXPIRED` assignments in the specified pool.

```python
toloka_client.find_assignments(pool_id='1', status = ['SKIPPED', 'EXPIRED'])
```
