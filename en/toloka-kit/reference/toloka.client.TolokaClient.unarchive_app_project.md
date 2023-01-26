# unarchive_app_project
`toloka.client.TolokaClient.unarchive_app_project` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/__init__.py#L3621)

```python
unarchive_app_project(self, app_project_id: str)
```

Unarchives an App project.


Previous project status, which was before archiving, is restored.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project.</p>

* **Returns:**

  The App project with updated status.

* **Return type:**

  [AppProject](toloka.client.app.AppProject.md)
