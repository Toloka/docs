# PoolSearchRequest
`toloka.client.search_requests.PoolSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/search_requests.py#L223)

```python
PoolSearchRequest(
    self,
    status: Optional[Pool.Status] = None,
    project_id: Optional[str] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None,
    last_started_lt: Optional[datetime] = None,
    last_started_lte: Optional[datetime] = None,
    last_started_gt: Optional[datetime] = None,
    last_started_gte: Optional[datetime] = None
)
```

Parameters for searching pools.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`status`|**Optional\[[Pool.Status](toloka.client.pool.Pool.Status.md)\]**|<p>Pool status. Refer to the [Pool.Status](toloka.client.pool.Pool.Status.md) page for more information on the available `status` values.</p>
`project_id`|**Optional\[str\]**|<p>Pools belonging to the project with the specified ID.</p>
`id_lt`|**Optional\[str\]**|<p>Pools with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Pools with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Pools with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Pools with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Pools created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Pools created before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Pools created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Pools created after or on the specified date.</p>
`last_started_lt`|**Optional\[datetime\]**|<p>Pools that were opened last time before the specified date.</p>
`last_started_lte`|**Optional\[datetime\]**|<p>Pools that were opened last time before or on the specified date.</p>
`last_started_gt`|**Optional\[datetime\]**|<p>Pools that were opened last time after the specified date.</p>
`last_started_gte`|**Optional\[datetime\]**|<p>Pools that were opened last time after or on the specified date.</p>
