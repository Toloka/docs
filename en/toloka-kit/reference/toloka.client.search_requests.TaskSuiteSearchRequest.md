# TaskSuiteSearchRequest
`toloka.client.search_requests.TaskSuiteSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/search_requests.py#L545)

```python
TaskSuiteSearchRequest(
    self,
    task_id: Optional[str] = None,
    pool_id: Optional[str] = None,
    overlap: Optional[int] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None,
    overlap_lt: Optional[int] = None,
    overlap_lte: Optional[int] = None,
    overlap_gt: Optional[int] = None,
    overlap_gte: Optional[int] = None
)
```

Parameters for searching task suites.

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
