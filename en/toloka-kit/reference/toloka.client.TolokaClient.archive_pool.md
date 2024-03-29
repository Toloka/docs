# archive_pool
`toloka.client.TolokaClient.archive_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L1413)

```python
archive_pool(self, pool_id: str)
```

Archives a pool.


Only closed pools can be archived.

You can't open archived pools, but you can [clone](toloka.client.TolokaClient.clone_pool.md) them if needed.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool to be archived.</p>

* **Returns:**

  The pool with updated status.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**


```python
closed_pool = next(toloka_client.get_pools(status='CLOSED'))
toloka_client.archive_pool(pool_id=closed_pool.id)
```
