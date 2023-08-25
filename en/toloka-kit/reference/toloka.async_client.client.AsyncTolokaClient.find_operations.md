# find_operations
`toloka.async_client.client.AsyncTolokaClient.find_operations` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L0)

Finds operations that match certain criteria.


The number of returned operations is limited. To find remaining operations call `find_operations` with updated search criteria.

To iterate over all matching operations you may use the [get_operations](toloka.client.TolokaClient.get_operations.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`type`|**Optional\[[OperationType](toloka.client.operations.OperationType.md)\]**|<p>Operation type. Refer to the [OperationType](toloka.client.operations.OperationType.md) page for more information on the available `type` values.</p>
`status`|**Optional\[[Operation.Status](toloka.client.operations.Operation.Status.md)\]**|<p>The status of the operation. Refer to the [Operation.Status](toloka.client.operations.Operation.Status.md) page for more information on the available `status` values.</p>
`id_lt`|**Optional\[str\]**|<p>Operations with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Operations with IDs less than or equal to the specified value.</p>
`id_gt`|**Optional\[str\]**|<p>Operations with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Operations with IDs greater than or equal to the specified value.</p>
`submitted_lt`|**Optional\[datetime\]**|<p>Operations submitted before the specified date.</p>
`submitted_lte`|**Optional\[datetime\]**|<p>Operations submitted before or on the specified date.</p>
`submitted_gt`|**Optional\[datetime\]**|<p>Operations submitted after the specified date.</p>
`submitted_gte`|**Optional\[datetime\]**|<p>Operations submitted after or on the specified date.</p>
`finished_lt`|**Optional\[datetime\]**|<p>Operations finished before the specified date.</p>
`finished_lte`|**Optional\[datetime\]**|<p>Operations finished before or on the specified date.</p>
`finished_gt`|**Optional\[datetime\]**|<p>Operations finished after the specified date.</p>
`finished_gte`|**Optional\[datetime\]**|<p>Operations finished after or on the specified date.</p>
`sort`|**Union\[List\[str\], [OperationSortItems](toloka.client.search_requests.OperationSortItems.md), None\]**|<p>Sorting options. Default: `None`.</p>
`limit`|**Optional\[int\]**|<p>Returned operations limit. The maximum allowed value: 500. The default value: 50.</p>

* **Returns:**

  Found operations and a flag showing whether there are more matching operations exceeding the limit.

* **Return type:**

  [OperationSearchResult](toloka.client.search_results.OperationSearchResult.md)

**Examples:**


```python
find_result = toloka_client.find_operations(
    type='POOL.OPEN', status='SUCCESS', sort=['-finished'], limit=3
)
operations = find_result.items
```
