# patch_app_batch
`toloka.async_client.client.AsyncTolokaClient.patch_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L0)

Updates an App batch.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the App project containing the batch.</p>
`batch_id`|**str**|<p>The ID of the batch.</p>
`name`|**Optional\[str\]**|<p>The new batch name.</p>
`priority_order`|**Optional\[[AppBatch.PriorityOrder](toloka.client.app.AppBatch.PriorityOrder.md)\]**|<p>The batch priority. See [PriorityOrder](toloka.client.app.AppBatch.PriorityOrder.md) for details.</p>

* **Returns:**

  The updated App batch.

* **Return type:**

  [AppBatch](toloka.client.app.AppBatch.md)

**Examples:**

Changing the batch name.

```python
batch = toloka_client.patch_app_batch(
    app_project_id='Q2d15QBjpwWuDz8Z321g',
    batch_id='4Va2BBWKL88S4QyAgVje',
    name = 'Preliminary batch'
)
```
