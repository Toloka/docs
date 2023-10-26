# open_pool
`toloka.client.TolokaClient.open_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L1780)

```python
open_pool(self, pool_id: str)
```

Opens a pool.


After opening the pool, tasks can be assigned to Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool.</p>

* **Returns:**

  The pool with updated status.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**

Opening a pool.

```python
toloka_client.open_pool(pool_id='1080020')
```
