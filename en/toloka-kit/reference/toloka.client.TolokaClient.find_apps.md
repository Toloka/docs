# find_apps
`toloka.client.TolokaClient.find_apps` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L3845)

Finds App solutions that match certain criteria.


The number of returned solutions is limited. To find remaining solutions call `find_apps` with updated search criteria.

To iterate over all matching solutions you may use the [get_apps](toloka.client.TolokaClient.get_apps.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`after_id`|**Optional\[str\]**|<p>The ID of a solution used for cursor pagination.</p>
`lang`|**Optional\[str\]**|<p>ISO 639 language code.</p>
`id_gt`|**Optional\[str\]**|<p>Solutions with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Solutions with IDs greater than or equal to the specified value.</p>
`id_lt`|**Optional\[str\]**|<p>Solutions with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Solutions with IDs less than or equal to the specified value.</p>
`name_gt`|**-**|<p>Solutions with names lexicographically greater than the specified value.</p>
`name_gte`|**-**|<p>Solutions with names lexicographically greater than or equal to the specified value.</p>
`name_lt`|**-**|<p>Solutions with names lexicographically less than the specified value.</p>
`name_lte`|**-**|<p>Solutions with names lexicographically less than or equal to the specified value.</p>
`sort`|**Union\[List\[str\], [AppSortItems](toloka.client.search_requests.AppSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned solutions limit. The maximum allowed limit is 1000.</p>

* **Returns:**

  Found solutions and a flag showing whether there are more matching solutions exceeding the limit.

* **Return type:**

  [AppSearchResult](toloka.client.search_results.AppSearchResult.md)

**Examples:**


```python
search = toloka_client.find_apps()
for app in search.content:
    print(app.id, app.name)

if search.has_more:
    print('There are more App solutions...')
```
