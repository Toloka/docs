# close_pool_for_update
`toloka.async_client.client.AsyncTolokaClient.close_pool_for_update` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/async_client/client.py#L0)

```python
async close_pool_for_update(self, pool_id: str)
```

Closes pool for update

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>ID of the pool that will be closed for update.</p>

* **Returns:**

  Pool object with new status.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**


```python
toloka_client.close_pool_for_update(pool_id='1')
```
