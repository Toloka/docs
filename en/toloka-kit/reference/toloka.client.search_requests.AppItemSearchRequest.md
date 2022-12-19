# AppItemSearchRequest
`toloka.client.search_requests.AppItemSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/search_requests.py#L1064)

```python
AppItemSearchRequest(
    self,
    after_id: Optional[str] = None,
    batch_id: Optional[str] = None,
    status: Optional[AppItem.Status] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None,
    finished_lt: Optional[datetime] = None,
    finished_lte: Optional[datetime] = None,
    finished_gt: Optional[datetime] = None,
    finished_gte: Optional[datetime] = None
)
```

Parameters for searching App task items.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`after_id`|**Optional\[str\]**|<p>The ID of the item used for cursor pagination.</p>
`batch_id`|**Optional\[str\]**|<p>The ID of the batch to look in.</p>
`status`|**Optional\[[AppItem.Status](toloka.client.app.AppItem.Status.md)\]**|<p>App task item status. Refer to the [AppItem.Status](toloka.client.app.AppItem.Status.md) page for more information on the available `status` values.</p>
`id_gt`|**Optional\[str\]**|<p>Items with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Items with IDs greater than or equal to the specified value.</p>
`id_lt`|**Optional\[str\]**|<p>Items with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Items with IDs less than or equal to the specified value.</p>
`created_gt`|**Optional\[datetime\]**|<p>Items created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Items created after or on the specified date.</p>
`created_lt`|**Optional\[datetime\]**|<p>Items created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Items created before or on the specified date.</p>
`finished_gt`|**Optional\[datetime\]**|<p>Items labeled after the specified date.</p>
`finished_gte`|**Optional\[datetime\]**|<p>Items labeled after or on the specified date.</p>
`finished_lt`|**Optional\[datetime\]**|<p>Items labeled before the specified date.</p>
`finished_lte`|**Optional\[datetime\]**|<p>Items labeled before or on the specified date.</p>
