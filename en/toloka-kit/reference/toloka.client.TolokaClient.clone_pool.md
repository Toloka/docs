# clone_pool
`toloka.client.TolokaClient.clone_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L1592)

```python
clone_pool(self, pool_id: str)
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
new_pool = toloka_client.clone_pool(pool_id='1080020')
```
