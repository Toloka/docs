# get_app_project
`toloka.async_client.client.AsyncTolokaClient.get_app_project` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/async_client/client.py#L0)

```python
async get_app_project(self, app_project_id: str)
```

Gets information from Toloka about an App project.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project.</p>

* **Returns:**

  The App project.

* **Return type:**

  [AppProject](toloka.client.app.AppProject.md)

**Examples:**


```python
app_project = toloka_client.get_app_project('Q2d15QBjpwWuDz8Z321g')
print(app_project.created, app_project.name)
```
