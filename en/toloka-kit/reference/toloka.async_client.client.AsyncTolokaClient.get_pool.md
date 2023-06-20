# get_pool
`toloka.async_client.client.AsyncTolokaClient.get_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/async_client/client.py#L0)

```python
async get_pool(self, pool_id: str)
```

Gets pool data from Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool.</p>

* **Returns:**

  The pool.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**


```python
toloka_client.get_pool(pool_id='1')
```
