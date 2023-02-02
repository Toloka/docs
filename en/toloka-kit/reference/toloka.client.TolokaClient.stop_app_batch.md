# stop_app_batch
`toloka.client.TolokaClient.stop_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/__init__.py#L3980)

```python
stop_app_batch(
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
