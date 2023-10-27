# update_project
`toloka.async_client.client.AsyncTolokaClient.update_project` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/async_client/client.py#L0)

```python
async update_project(
    self,
    project_id: str,
    project: Project
)
```

Updates all project parameters in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`project_id`|**str**|<p>The ID of the project to be updated.</p>
`project`|**[Project](toloka.client.project.Project.md)**|<p>The project with new parameters.</p>

* **Returns:**

  The project with updated parameters.

* **Return type:**

  [Project](toloka.client.project.Project.md)

**Examples:**


```python
updated_project = toloka_client.get_project(project_id='92694')
updated_project.private_comment = 'example project'
updated_project = toloka_client.update_project(project_id=updated_project.id, project=updated_project)
```
