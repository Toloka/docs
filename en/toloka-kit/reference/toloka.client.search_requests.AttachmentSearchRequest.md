# AttachmentSearchRequest
`toloka.client.search_requests.AttachmentSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/search_requests.py#L596)

```python
AttachmentSearchRequest(
    self,
    name: Optional[str] = None,
    type: Optional[Attachment.Type] = None,
    user_id: Optional[str] = None,
    assignment_id: Optional[str] = None,
    pool_id: Optional[str] = None,
    owner_id: Optional[str] = None,
    owner_company_id: Optional[str] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None
)
```

Parameters for searching attachments.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`name`|**Optional\[str\]**|<p>An attachment file name.</p>
`type`|**Optional\[[Attachment.Type](toloka.client.attachment.Attachment.Type.md)\]**|<p>An attachment type. Refer to the [Attachment.Type](toloka.client.attachment.Attachment.Type.md) page for more information on the available `type` values.</p>
`user_id`|**Optional\[str\]**|<p>The ID of a Toloker who uploaded attachments.</p>
`assignment_id`|**Optional\[str\]**|<p>The ID of an assignment with attachments. Either `assignment_id` of `pool_id` is required in a search request.</p>
`pool_id`|**Optional\[str\]**|<p>The ID of a pool with attachments. Either `assignment_id` of `pool_id` is required in a search request.</p>
`id_lt`|**Optional\[str\]**|<p>Attachments with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Attachments with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Attachments with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Attachments with IDs greater than or equal to the specified value.</p>
`created_lt`|**Optional\[datetime\]**|<p>Attachments uploaded by Tolokers before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Attachments uploaded by Tolokers before or on the specified date.</p>
`created_gt`|**Optional\[datetime\]**|<p>Attachments uploaded by Tolokers after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Attachments uploaded by Tolokers after or on the specified date.</p>
