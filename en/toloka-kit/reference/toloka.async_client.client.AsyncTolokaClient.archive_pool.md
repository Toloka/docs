# archive_pool
`toloka.async_client.client.AsyncTolokaClient.archive_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/async_client/client.py#L0)

```python
async archive_pool(self, pool_id: str)
```

Sends pool to archive


The pool must be in the status "closed".
The archived pool is not deleted. You can access it when you will need it.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>ID of pool that will be archived.</p>

* **Returns:**

  Object with updated status.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**


```python
closed_pool = next(toloka_client.get_pools(status='CLOSED'))
toloka_client.archive_pool(pool_id=closed_pool.id)
```
