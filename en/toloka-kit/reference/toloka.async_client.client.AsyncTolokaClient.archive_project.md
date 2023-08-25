# archive_project
`toloka.async_client.client.AsyncTolokaClient.archive_project` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/async_client/client.py#L0)

```python
async archive_project(self, project_id: str)
```

Archives a project.


All pools in the project must be archived before archiving the project.

The archived project is not deleted. You can access it if you need.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`project_id`|**str**|<p>The ID of project to be archived.</p>

* **Returns:**

  The project with the updated status.

* **Return type:**

  [Project](toloka.client.project.Project.md)

**Examples:**


```python
archived_project = toloka_client.archive_project('117493')
```
