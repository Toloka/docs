# close_pool_for_update_async
`toloka.async_client.client.AsyncTolokaClient.close_pool_for_update_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/async_client/client.py#L0)

```python
async close_pool_for_update_async(self, pool_id: str)
```

Closes a pool that is to be updated. Sends an asynchronous request to Toloka.


To make changes to a pool, close it before updating parameters.
If you don't open the pool after updating, it opens automatically in 15 minutes.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool to be closed.</p>

* **Returns:**

  An object to track the progress of the operation. If the pool is already closed then `None` is returned.

* **Return type:**

  Optional\[[PoolCloseOperation](toloka.client.operations.PoolCloseOperation.md)\]

**Examples:**


```python
close_op = toloka_client.close_pool_for_update_async(pool_id='1')
toloka_client.wait_operation(close_op)
```
