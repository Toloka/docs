# get_project
`toloka.client.TolokaClient.get_project` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L1261)

```python
get_project(self, project_id: str)
```

Gets project data from Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`project_id`|**str**|<p>The ID of the project.</p>

* **Returns:**

  The project.

* **Return type:**

  [Project](toloka.client.project.Project.md)

**Examples:**


```python
project = toloka_client.get_project(project_id='92694')
```
