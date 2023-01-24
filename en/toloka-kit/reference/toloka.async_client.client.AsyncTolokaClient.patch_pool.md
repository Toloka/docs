# patch_pool
`toloka.async_client.client.AsyncTolokaClient.patch_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/__init__.py#L0)

Changes pool parameters in Toloka.


If a parameter is not specified in the `patch_pool` method, then it is left unchanged in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool to be changed.</p>
`priority`|**Optional\[int\]**|<p>The new priority of the pool. Possible values: from -100 to 100.</p>

* **Returns:**

  The pool with updated parameters.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**

Changing priority of a pool.

```python
toloka_client.patch_pool(pool_id='1', priority=100)
```
