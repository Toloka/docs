# archive_app_project
`toloka.async_client.client.AsyncTolokaClient.archive_app_project` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/async_client/client.py#L0)

```python
async archive_app_project(self, app_project_id: str)
```

Archives an App project.


The project changes its status to `ARCHIVED`.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project.</p>

* **Returns:**

  The App project with updated status.

* **Return type:**

  [AppProject](toloka.client.app.AppProject.md)

**Examples:**


```python
toloka_client.archive_app_project('Q2d15QBjpwWuDz8Z321g')
```
