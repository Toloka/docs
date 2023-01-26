# AggregatedSolutionSearchRequest
`toloka.client.search_requests.AggregatedSolutionSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/search_requests.py#L470)

```python
AggregatedSolutionSearchRequest(
    self,
    task_id_lt: Optional[str] = None,
    task_id_lte: Optional[str] = None,
    task_id_gt: Optional[str] = None,
    task_id_gte: Optional[str] = None
)
```

Parameters for searching aggregated responses.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`task_id_lt`|**Optional\[str\]**|<p>Responses for tasks with IDs less than the specified value.</p>
`task_id_lte`|**Optional\[str\]**|<p>Responses for tasks with IDs less than or equal to the specified value.</p>
`task_id_gt`|**Optional\[str\]**|<p>Responses for tasks with IDs greater than the specified value.</p>
`task_id_gte`|**Optional\[str\]**|<p>Responses for tasks with IDs greater than or equal to the specified value.</p>
