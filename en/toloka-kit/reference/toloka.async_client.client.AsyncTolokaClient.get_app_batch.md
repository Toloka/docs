# get_app_batch
`toloka.async_client.client.AsyncTolokaClient.get_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/async_client/client.py#L0)

```python
async get_app_batch(
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

**Examples:**


```python
batch = toloka_client.get_app_batch(
    app_project_id='Q2d15QBjpwWuDz8Z321g',
    app_batch_id='4Va2BBWKL88S4QyAgVje'
)
print(batch.status, batch.items_count, batch.cost)
```
