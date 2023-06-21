# AppBatchSearchRequest
`toloka.client.search_requests.AppBatchSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/search_requests.py#L1111)

```python
AppBatchSearchRequest(
    self,
    after_id: Optional[str] = None,
    status: Optional[AppBatch.Status] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    name_lt: Optional[str] = None,
    name_lte: Optional[str] = None,
    name_gt: Optional[str] = None,
    name_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None
)
```

Parameters for searching batches in an App project.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`after_id`|**Optional\[str\]**|<p>The ID of the batch used for cursor pagination.</p>
`status`|**Optional\[[AppBatch.Status](toloka.client.app.AppBatch.Status.md)\]**|<p>Refer to the [AppBatch.Status](toloka.client.app.AppBatch.Status.md) page for more information on the available `status` values.</p>
`id_gt`|**Optional\[str\]**|<p>Batches with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Batches with IDs greater than or equal to the specified value.</p>
`id_lt`|**Optional\[str\]**|<p>Batches with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Batches with IDs less than or equal to the specified value.</p>
`name_gt`|**Optional\[str\]**|<p>Batches with names lexicographically greater than the specified value.</p>
`name_gte`|**Optional\[str\]**|<p>Batches with names lexicographically greater than or equal to the specified value.</p>
`name_lt`|**Optional\[str\]**|<p>Batches with names lexicographically less than the specified value.</p>
`name_lte`|**Optional\[str\]**|<p>Batches with names lexicographically less than or equal to the specified value.</p>
`created_gt`|**Optional\[datetime\]**|<p>Batches created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Batches created after or on the specified date.</p>
`created_lt`|**Optional\[datetime\]**|<p>Batches created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Batches created before or on the specified date.</p>
