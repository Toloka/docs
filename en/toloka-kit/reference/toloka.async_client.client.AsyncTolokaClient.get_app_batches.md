# get_app_batches
`toloka.async_client.client.AsyncTolokaClient.get_app_batches` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/__init__.py#L0)

Finds all batches that match certain criteria in an App project.


`get_app_batches` returns a generator. You can iterate over all found batches using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort batches use the [find_app_batches](toloka.client.TolokaClient.find_app_batches.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the App project.</p>
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
`batch_size`|**Optional\[int\]**|<p>Returned app batches limit for each request. The maximum allowed batch_size is 1000.</p>

* **Yields:**

  The next matching batch.

* **Yield type:**

  [AsyncGenAdapter](toloka.util.async_utils.AsyncGenAdapter.md)\[[AppBatch](toloka.client.app.AppBatch.md), None\]

**Examples:**


```python
batches = toloka_client.get_app_batches(app_project_id = 'Q2d15QBjpwWuDz8Z321g', status = 'NEW')
for batch in batches:
    print(batch.id, batch.status, batch.items_count)
```
