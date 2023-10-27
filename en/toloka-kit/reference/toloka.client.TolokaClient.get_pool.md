# get_pool
`toloka.client.TolokaClient.get_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L1731)

```python
get_pool(self, pool_id: str)
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
pool = toloka_client.get_pool(pool_id='1080020')
print(pool.private_name, pool.status)
```
