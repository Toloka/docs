# archive_app_project
`toloka.client.TolokaClient.archive_app_project` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L3799)

```python
archive_app_project(self, app_project_id: str)
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
