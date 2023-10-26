# unarchive_app_batch
`toloka.client.TolokaClient.unarchive_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L4390)

```python
unarchive_app_batch(
    self,
    app_project_id: str,
    batch_id: str
)
```

Changes the batch status to the last one it had before archiving. After the operation, you can process the


batch again.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project with which the batch is associated.</p>
`batch_id`|**str**|<p>The ID of the batch you want to unarchive.</p>

**Examples:**


```python
toloka_client.unarchive_app_batch(
    app_project_id='Q2d15QBjpwWuDz8Z321g',
    batch_id='4Va2BBWKL88S4QyAgVje'
)
```
