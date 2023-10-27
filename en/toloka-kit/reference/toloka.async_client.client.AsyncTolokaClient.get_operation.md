# get_operation
`toloka.async_client.client.AsyncTolokaClient.get_operation` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/async_client/client.py#L0)

```python
async get_operation(self, operation_id: str)
```

Gets information about an operation from Toloka.


Some API requests, for example uploading tasks or opening a pool, are processed as asynchronous operations that run in the background.
You can track their progress or wait for them to complete by calling the [wait_operation](toloka.client.TolokaClient.wait_operation.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operation_id`|**str**|<p>The ID of the operation.</p>

* **Returns:**

  The operation.

* **Return type:**

  [Operation](toloka.client.operations.Operation.md)

**Examples:**


```python
operation = toloka_client.get_operation(operation_id='6d84114f-fcfc-473d-8249-1a4f3ea550eb')
print(operation.status, operation.finished)
```
