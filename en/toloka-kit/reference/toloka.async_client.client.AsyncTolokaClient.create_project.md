# create_project
`toloka.async_client.client.AsyncTolokaClient.create_project` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/async_client/client.py#L0)

```python
async create_project(self, project: Project)
```

Creates a new project in Toloka.


You can send a maximum of 20 requests of this kind per minute and a maximum of 100 requests per day.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`project`|**[Project](toloka.client.project.Project.md)**|<p>The project to be created.</p>

* **Returns:**

  The project with updated read-only fields.

* **Return type:**

  [Project](toloka.client.project.Project.md)

**Examples:**

Creating a new project.

```python
new_project = toloka.client.project.Project(
    assignments_issuing_type=toloka.client.project.Project.AssignmentsIssuingType.AUTOMATED,
    public_name='Describe the image',
    public_description='Describe the image',
    public_instructions='Describe in a few words what is happening in the image.',
    task_spec=toloka.client.project.task_spec.TaskSpec(
        input_spec={'image': toloka.client.project.field_spec.UrlSpec()},
        output_spec={'result': toloka.client.project.field_spec.StringSpec()},
        view_spec=project_interface,
    ),
)
new_project = toloka_client.create_project(new_project)
print(new_project.id)
```
