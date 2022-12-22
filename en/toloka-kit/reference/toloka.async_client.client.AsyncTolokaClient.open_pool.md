# open_pool
`toloka.async_client.client.AsyncTolokaClient.open_pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/async_client/client.py#L0)

```python
async open_pool(self, pool_id: str)
```

Starts distributing tasks from the pool


Tolokers will see your tasks only after that call.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>ID of the pool that will be started.</p>

* **Returns:**

  Pool object with new status.

* **Return type:**

  [Pool](toloka.client.pool.Pool.md)

**Examples:**

Open the pool for Tolokers.

```python
toloka_client.open_pool(pool_id='1')
```
