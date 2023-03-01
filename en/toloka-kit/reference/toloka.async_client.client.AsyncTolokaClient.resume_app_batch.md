# resume_app_batch
`toloka.async_client.client.AsyncTolokaClient.resume_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/async_client/client.py#L0)

```python
async resume_app_batch(
    self,
    app_project_id: str,
    batch_id: str
)
```

Resumes annotation of a batch of task items in an App project.


Processing can be resumed only for the batch with the STOPPING or STOPPED status.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project.</p>
`batch_id`|**str**|<p>The ID of the batch.</p>
