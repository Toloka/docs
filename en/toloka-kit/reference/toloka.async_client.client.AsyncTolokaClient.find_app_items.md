# find_app_items
`toloka.async_client.client.AsyncTolokaClient.find_app_items` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L0)

Finds task items that match certain criteria in an App project.


The number of returned items is limited. To find remaining items call `find_app_items` with updated search criteria.

To iterate over all matching items you may use the [get_app_items](toloka.client.TolokaClient.get_app_items.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the App project.</p>
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
`sort`|**Union\[List\[str\], [AppItemSortItems](toloka.client.search_requests.AppItemSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned items limit. The maximum allowed limit is 1000.</p>

* **Returns:**

  Found task items and a flag showing whether there are more matching items exceeding the limit.

* **Return type:**

  [AppItemSearchResult](toloka.client.search_results.AppItemSearchResult.md)
