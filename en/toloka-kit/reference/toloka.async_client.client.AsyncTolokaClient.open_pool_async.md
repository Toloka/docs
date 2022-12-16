# open_pool_async
`toloka.async_client.client.AsyncTolokaClient.open_pool_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/async_client/client.py#L0)

```python
async open_pool_async(self, pool_id: str)
```

Starts distributing tasks from the pool, asynchronous version


Tolokers will see your tasks only after that call.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>ID of the pool that will be started.</p>

* **Returns:**

  An operation upon completion of which you can get the pool with new status. If pool is
already opened then None is returned.

* **Return type:**

  Optional\[[PoolOpenOperation](toloka.client.operations.PoolOpenOperation.md)\]

**Examples:**

Open the pool for Tolokers.

```python
open_pool = toloka_client.open_pool(pool_id='1')
toloka_client.wait_operation(open_pool)
```
