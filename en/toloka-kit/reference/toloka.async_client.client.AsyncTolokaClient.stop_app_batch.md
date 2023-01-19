# stop_app_batch
`toloka.async_client.client.AsyncTolokaClient.stop_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/async_client/client.py#L0)

```python
async stop_app_batch(
    self,
    app_project_id: str,
    batch_id: str
)
```

Stops annotation of a batch of task items in an App project.


Processing can be stopped only for the batch with the PROCESSING status.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project.</p>
`batch_id`|**str**|<p>The ID of the batch.</p>
