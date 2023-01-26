# clone_pool_async
`toloka.async_client.client.AsyncTolokaClient.clone_pool_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/async_client/client.py#L0)

```python
async clone_pool_async(self, pool_id: str)
```

Clones an existing pool. Sends an asynchronous request to Toloka.


An empty pool with the same parameters is created.
The new pool is attached to the same project.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>The ID of the pool to be cloned.</p>

* **Returns:**

  An object to track the progress of the operation.

* **Return type:**

  [PoolCloneOperation](toloka.client.operations.PoolCloneOperation.md)

**Examples:**


```python
clone_op = toloka_client.clone_pool_async(pool_id='1')
toloka_client.wait_operation(clone_op)
```
