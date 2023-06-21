# close_pool_for_update
`toloka.client.TolokaClient.close_pool_for_update` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/__init__.py#L1477)

```python
close_pool_for_update(self, pool_id: str)
```

Closes a pool that is to be updated.


To make changes to a pool, close it before updating parameters.
If you don't open the pool after updating, it opens automatically in 15 minutes.

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
toloka_client.close_pool_for_update(pool_id='1')
```
