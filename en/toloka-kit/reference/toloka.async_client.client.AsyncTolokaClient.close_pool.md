# close_pool
`toloka.async_client.client.AsyncTolokaClient.close_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/async_client/client.py#L0)

```python
async close_pool(self, pool_id: str)
```

Closes a pool.


If all tasks in a pool are completed, then the pool is closed automatically.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool to be closed.</p>

* **Returns:**

  The pool with updated status.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**


```python
open_pool = next(toloka_client.get_pools(status='OPEN'))
toloka_client.close_pool(pool_id=open_pool.id)
```
