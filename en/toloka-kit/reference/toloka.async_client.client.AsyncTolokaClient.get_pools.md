# get_pools
`toloka.async_client.client.AsyncTolokaClient.get_pools` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L0)

Finds all pools that match certain criteria.


`get_pools` returns a generator. You can iterate over all found pools using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort pools use the [find_pools](toloka.client.TolokaClient.find_pools.md) method.

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

* **Yields:**

  The next matching pool.

* **Yield type:**

  [AsyncGenAdapter](toloka.util.async_utils.AsyncGenAdapter.md)\[[Pool](toloka.client.pool.Pool.md), None\]

**Examples:**

How to get all open pools from a project.

```python
open_pools = toloka_client.get_pools(project_id='1', status='OPEN')
```

How to get all pools from a project.

```python
all_pools = toloka_client.get_pools(project_id='1')
```
