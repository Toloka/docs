# start_sync_batch_processing
`toloka.async_client.client.AsyncTolokaClient.start_sync_batch_processing` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/async_client/client.py#L0)

```python
async start_sync_batch_processing(
    self,
    app_project_id: str,
    request: SyncBatchCreateRequest
)
```

Starts processing the batch with the ID specified in the request.


This batch processing is applicable for solutions which use synchronous protocols only.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project with which the batch is associated.</p>

* **Returns:**

  The response to the request to start sync batch processing.

* **Return type:**

  [AppBatch](toloka.client.app.AppBatch.md)
