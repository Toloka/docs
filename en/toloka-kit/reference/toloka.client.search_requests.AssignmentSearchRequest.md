# AssignmentSearchRequest
`toloka.client.search_requests.AssignmentSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/search_requests.py#L367)

```python
AssignmentSearchRequest(
    self,
    status: Union[str, Assignment.Status, List[Union[str, Assignment.Status]], None] = None,
    task_id: Optional[str] = None,
    task_suite_id: Optional[str] = None,
    pool_id: Optional[str] = None,
    user_id: Optional[str] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None,
    submitted_lt: Optional[datetime] = None,
    submitted_lte: Optional[datetime] = None,
    submitted_gt: Optional[datetime] = None,
    submitted_gte: Optional[datetime] = None,
    accepted_lt: Optional[datetime] = None,
    accepted_lte: Optional[datetime] = None,
    accepted_gt: Optional[datetime] = None,
    accepted_gte: Optional[datetime] = None,
    rejected_lt: Optional[datetime] = None,
    rejected_lte: Optional[datetime] = None,
    rejected_gt: Optional[datetime] = None,
    rejected_gte: Optional[datetime] = None,
    skipped_lt: Optional[datetime] = None,
    skipped_lte: Optional[datetime] = None,
    skipped_gt: Optional[datetime] = None,
    skipped_gte: Optional[datetime] = None,
    expired_lt: Optional[datetime] = None,
    expired_lte: Optional[datetime] = None,
    expired_gt: Optional[datetime] = None,
    expired_gte: Optional[datetime] = None
)
```

Parameters for searching task suites assignments.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`status`|**Optional\[List\[[Assignment.Status](toloka.client.assignment.Assignment.Status.md)\]\]**|<p>Assignment status or a list of statuses. Refer to the [Assignment.Status](toloka.client.assignment.Assignment.Status.md) page for more information on the available `status` values.</p>
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
