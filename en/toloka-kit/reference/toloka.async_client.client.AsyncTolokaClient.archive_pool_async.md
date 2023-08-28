# archive_pool_async
`toloka.async_client.client.AsyncTolokaClient.archive_pool_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/async_client/client.py#L0)

```python
async archive_pool_async(self, pool_id: str)
```

Archives a pool. Sends an asynchronous request to Toloka.


Only closed pools can be archived.

You can't open archived pools, but you can [clone](toloka.client.TolokaClient.clone_pool.md) them if needed.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool to be archived.</p>

* **Returns:**

  An object to track the progress of the operation. If the pool is already archived then `None` is returned.

* **Return type:**

  Optional\[[PoolArchiveOperation](toloka.client.operations.PoolArchiveOperation.md)\]

**Examples:**


```python
closed_pool = next(toloka_client.get_pools(status='CLOSED'))
archive_op = toloka_client.archive_pool_async(pool_id=closed_pool.id)
toloka_client.wait_operation(archive_op)
```
