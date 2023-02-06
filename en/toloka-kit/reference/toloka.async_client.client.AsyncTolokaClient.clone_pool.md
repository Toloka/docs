# clone_pool
`toloka.async_client.client.AsyncTolokaClient.clone_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/async_client/client.py#L0)

```python
async clone_pool(self, pool_id: str)
```

Clones an existing pool.


An empty pool with the same parameters is created.
The new pool is attached to the same project.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool to be cloned.</p>

* **Returns:**

  The new pool.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**


```python
toloka_client.clone_pool(pool_id='1')
```
