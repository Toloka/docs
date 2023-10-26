# get_operations
`toloka.client.TolokaClient.get_operations` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L3061)

Finds all operations that match certain criteria.


`get_operations` returns a generator. You can iterate over all found operations using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort operations use the [find_operations](toloka.client.TolokaClient.find_operations.md) method.

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
`batch_size`|**Optional\[int\]**|<p>A limit of items returned by each request to Toloka. The maximum allowed value: 500. The default value: 50.</p>

* **Yields:**

  The next matching operation.

* **Yield type:**

  Generator\[[Operation](toloka.client.operations.Operation.md), None, None\]

**Examples:**


```python
some_operations = list(toloka_client.get_operations(submitted_lt='2023-06-01T00:00:00'))
```
