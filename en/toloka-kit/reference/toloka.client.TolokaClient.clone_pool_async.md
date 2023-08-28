# clone_pool_async
`toloka.client.TolokaClient.clone_pool_async` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L1585)

```python
clone_pool_async(self, pool_id: str)
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
clone_op = toloka_client.clone_pool_async(pool_id='1080020')
toloka_client.wait_operation(clone_op)
```
