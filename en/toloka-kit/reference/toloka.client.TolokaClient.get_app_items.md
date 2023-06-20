# get_app_items
`toloka.client.TolokaClient.get_app_items` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L3983)

Finds all App task items that match certain criteria in an App project.


`get_app_items` returns a generator. You can iterate over all found items using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort items use the [find_app_items](toloka.client.TolokaClient.find_app_items.md) method.

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
`batch_size`|**Optional\[int\]**|<p>Returned items limit for each request. The maximum allowed batch_size is 1000.</p>

* **Yields:**

  The next matching item.

* **Yield type:**

  Generator\[[AppItem](toloka.client.app.AppItem.md), None, None\]

**Examples:**


```python
items = toloka_client.get_app_items('Q2d15QBjpwWuDz8Z321g')
for item in items:
    print(item.id, item.status, item.finished_at)
```
