# resume_app_batch
`toloka.async_client.client.AsyncTolokaClient.resume_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/async_client/client.py#L0)

```python
async resume_app_batch(
    self,
    app_project_id: str,
    batch_id: str
)
```

Resumes annotation of a batch of task items in an App project.


Processing can be resumed only for the batch with the `STOPPING` or `STOPPED` status.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project.</p>
`batch_id`|**str**|<p>The ID of the batch.</p>

**Examples:**


```python
toloka_client.resume_app_batch(app_project_id = 'Q2d15QBjpwWuDz8Z321g', batch_id = '4Va2BBWKL88S4QyAgVje')
```
