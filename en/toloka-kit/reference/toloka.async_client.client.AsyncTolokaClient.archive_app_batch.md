# archive_app_batch
`toloka.async_client.client.AsyncTolokaClient.archive_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/async_client/client.py#L0)

```python
async archive_app_batch(
    self,
    app_project_id: str,
    batch_id: str
)
```

Archives the batch with the ID specified in the request to hide its data.


You can archive the batches which are not currently being processed (are not in the `PROCESSING` status). You
must stop the batches before archiving them. The batch gets the `ARCHIVE` status.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project with which the batch is associated.</p>
`batch_id`|**str**|<p>The ID of the batch you want to archive.</p>

**Examples:**


```python
toloka_client.archive_app_batch(
    app_project_id='Q2d15QBjpwWuDz8Z321g',
    batch_id='4Va2BBWKL88S4QyAgVje'
)
```
