# get_app_batch
`toloka.client.TolokaClient.get_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/__init__.py#L3925)

```python
get_app_batch(
    self,
    app_project_id: str,
    batch_id: str
)
```

Gets information from Toloka about a batch in an App project.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project.</p>
`batch_id`|**str**|<p>The ID of the batch.</p>

* **Returns:**

  The App batch.

* **Return type:**

  [AppBatch](toloka.client.app.AppBatch.md)
