# find_app_batches
`toloka.client.TolokaClient.find_app_batches` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L4220)

Finds batches that match certain criteria in an App project.


The number of returned batches is limited. To find remaining batches call `find_app_batches` with updated search criteria.

To iterate over all matching batches you may use the [get_app_batches](toloka.client.TolokaClient.get_app_batches.md) method.

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
`sort`|**Union\[List\[str\], [AppBatchSortItems](toloka.client.search_requests.AppBatchSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned batches limit. The maximum allowed value: 1000.</p>

* **Returns:**

  Found batches and a flag showing whether there are more matching batches exceeding the limit.

* **Return type:**

  [AppBatchSearchResult](toloka.client.search_results.AppBatchSearchResult.md)

**Examples:**


```python
result = toloka_client.find_app_batches(
    app_project_id='Q2d15QBjpwWuDz8Z321g', status='NEW', sort='id'
)
batches = result.content
if result.has_more:
    print('There are more NEW batches...')
```
