# close_pool_async
`toloka.client.TolokaClient.close_pool_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/__init__.py#L1453)

```python
close_pool_async(self, pool_id: str)
```

Closes a pool. Sends an asynchronous request to Toloka.


If all tasks in a pool are completed, then the pool is closed automatically.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool to be closed.</p>

* **Returns:**

  An object to track the progress of the operation. If the pool is already closed then `None` is returned.

* **Return type:**

  Optional\[[PoolCloseOperation](toloka.client.operations.PoolCloseOperation.md)\]

**Examples:**


```python
open_pool = next(toloka_client.get_pools(status='OPEN'))
close_op = toloka_client.close_pool_async(pool_id=open_pool.id)
toloka_client.wait_operation(close_op)
```
