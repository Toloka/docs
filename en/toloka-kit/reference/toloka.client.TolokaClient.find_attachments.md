# find_attachments
`toloka.client.TolokaClient.find_attachments` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L879)

Finds attachments that match certain criteria and returns their metadata.


The number of returned attachments is limited. To find remaining attachments call `find_attachments` with updated search criteria.

To iterate over all matching attachments you may use the [get_attachments](toloka.client.TolokaClient.get_attachments.md) method.

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
`sort`|**Union\[List\[str\], [AttachmentSortItems](toloka.client.search_requests.AttachmentSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned attachments limit. The maximum allowed value: 100.</p>

* **Returns:**

  Found attachments and a flag showing whether there are more matching attachments exceeding the limit.

* **Return type:**

  [AttachmentSearchResult](toloka.client.search_results.AttachmentSearchResult.md)

**Examples:**

Let's find attachments in the pool and sort them by the ID and the date of creation in descending order.

```python
attachments = toloka_client.find_attachments(pool_id='1080020', sort=['-created', '-id'], limit=10)
```

If there are attachments exceeding the `limit`, then `attachments.has_more` is set to `True`.
