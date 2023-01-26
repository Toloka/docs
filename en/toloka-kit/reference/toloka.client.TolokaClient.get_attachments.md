# get_attachments
`toloka.client.TolokaClient.get_attachments` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/__init__.py#L823)

Finds all attachments that match certain criteria and returns their metadata.


`get_attachments` returns a generator. You can iterate over all found attachments using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort attachments use the [find_attachments](toloka.client.TolokaClient.find_attachments.md) method.

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
`batch_size`|**Optional\[int\]**|<p>Returned attachments limit for each request. The maximum allowed batch_size is 100.</p>

* **Yields:**

  The next matching attachment.

* **Yield type:**

  Generator\[[Attachment](toloka.client.attachment.Attachment.md), None, None\]

**Examples:**

Make a list of all received attachments in the specified pool.

```python
results_list = list(toloka_client.get_attachments(pool_id='1'))
```
