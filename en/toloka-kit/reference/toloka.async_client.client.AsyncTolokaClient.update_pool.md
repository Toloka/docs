# update_pool
`toloka.async_client.client.AsyncTolokaClient.update_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/async_client/client.py#L0)

```python
async update_pool(
    self,
    pool_id: str,
    pool: Pool
)
```

Updates all pool parameters in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool to be updated.</p>
`pool`|**[Pool](toloka.client.pool.Pool.md)**|<p>The pool with new parameters.</p>

* **Returns:**

  The pool with updated parameters.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**


```python
updated_pool = toloka_client.get_pool(pool_id='1')
updated_pool.will_expire = datetime.datetime.now(datetime.timezone.utc) + datetime.timedelta(days=30)
toloka_client.update_pool(pool_id=updated_pool.id, pool=updated_pool)
```
