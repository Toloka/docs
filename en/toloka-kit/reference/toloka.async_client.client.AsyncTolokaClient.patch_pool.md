# patch_pool
`toloka.async_client.client.AsyncTolokaClient.patch_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L0)

Changes the priority of the pool issue

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>ID of the pool that will be patched.</p>
`priority`|**Optional\[int\]**|<p>The priority of the pool in relation to other pools in the project with the same task price and set of filters. Tolokers are assigned tasks with a higher priority first. Possible values: from -100 to 100.</p>

* **Returns:**

  Object with updated priority.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**

Set the highest priority to a specified pool.

```python
toloka_client.patch_pool(pool_id='1', priority=100)
```
