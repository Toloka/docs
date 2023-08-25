# open_pool_async
`toloka.async_client.client.AsyncTolokaClient.open_pool_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/async_client/client.py#L0)

```python
async open_pool_async(self, pool_id: str)
```

Opens a pool. Sends an asynchronous request to Toloka.


After opening the pool, tasks can be assigned to Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool.</p>

* **Returns:**

  An object to track the progress of the operation. If the pool is already opened then `None` is returned.

* **Return type:**

  Optional\[[PoolOpenOperation](toloka.client.operations.PoolOpenOperation.md)\]

**Examples:**

Opening a pool.

```python
open_op = toloka_client.open_pool(pool_id='1080020')
toloka_client.wait_operation(open_op)
```
