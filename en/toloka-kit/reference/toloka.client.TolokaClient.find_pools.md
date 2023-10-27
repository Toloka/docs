# find_pools
`toloka.client.TolokaClient.find_pools` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L1686)

Finds pools that match certain criteria.


The number of returned pools is limited. To find remaining pools call `find_pools` with updated search criteria.

To iterate over all matching pools you may use the [get_pools](toloka.client.TolokaClient.get_pools.md) method.

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
`sort`|**Union\[List\[str\], [PoolSortItems](toloka.client.search_requests.PoolSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned pools limit. The maximum allowed value: 300. The default value: 20.</p>

* **Returns:**

  Found pools and a flag showing whether there are more matching pools exceeding the limit.

* **Return type:**

  [PoolSearchResult](toloka.client.search_results.PoolSearchResult.md)

**Examples:**

Finding all pools in all projects.

```python
find_result = toloka_client.find_pools()
pools = find_result.items
```

Finding all open pools in all projects.

```python
find_result = toloka_client.find_pools(status='OPEN')
pools = find_result.items
```

Finding open pools in a specific project.

```python
find_result = toloka_client.find_pools(status='OPEN', project_id='92694')
pools = find_result.items
```

If there are pools exceeding the `limit`, then `find_result.has_more` is set to `True`.
