# OperationSearchRequest
`toloka.client.search_requests.OperationSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/search_requests.py#L901)

```python
OperationSearchRequest(
    self,
    type: Optional[OperationType] = None,
    status: Optional[Operation.Status] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    submitted_lt: Optional[datetime] = None,
    submitted_lte: Optional[datetime] = None,
    submitted_gt: Optional[datetime] = None,
    submitted_gte: Optional[datetime] = None,
    finished_lt: Optional[datetime] = None,
    finished_lte: Optional[datetime] = None,
    finished_gt: Optional[datetime] = None,
    finished_gte: Optional[datetime] = None
)
```

Parameters for searching operations.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`type`|**Optional\[[OperationType](toloka.client.operations.OperationType.md)\]**|<p>Operation type. Refer to the [OperationType](toloka.client.operations.OperationType.md) page for more information on the available `type` values.</p>
`status`|**Optional\[[Operation.Status](toloka.client.operations.Operation.Status.md)\]**|<p>The status of the operation. Refer to the [Operation.Status](toloka.client.operations.Operation.Status.md) page for more information on the available `status` values.</p>
`id_lt`|**Optional\[str\]**|<p>Operations with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Operations with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Operations with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Operations with IDs greater than or equal to the specified value.</p>
`submitted_lt`|**Optional\[datetime\]**|<p>Operations submitted before the specified date.</p>
`submitted_lte`|**Optional\[datetime\]**|<p>Operations submitted before or on the specified date.</p>
`submitted_gt`|**Optional\[datetime\]**|<p>Operations submitted after the specified date.</p>
`submitted_gte`|**Optional\[datetime\]**|<p>Operations submitted after or on the specified date.</p>
`finished_lt`|**Optional\[datetime\]**|<p>Operations finished before the specified date.</p>
`finished_lte`|**Optional\[datetime\]**|<p>Operations finished before or on the specified date.</p>
`finished_gt`|**Optional\[datetime\]**|<p>Operations finished after the specified date.</p>
`finished_gte`|**Optional\[datetime\]**|<p>Operations finished after or on the specified date.</p>
