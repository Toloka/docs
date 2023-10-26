# check_update_project_for_major_version_change
`toloka.client.TolokaClient.check_update_project_for_major_version_change` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L1340)

```python
check_update_project_for_major_version_change(
    self,
    project_id: str,
    project: Project
)
```

Checks if the project update is a breaking change or not.


This method is similar to the `update_project` method, but instead of actually applying the changes it checks if
the update is a breaking change or not. If the update is a breaking change, every pool in the project will not
receive the current project update and any future project changes and will be tied to the last version of the
project before the breaking change happened.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`project_id`|**str**|<p>The ID of the project to be updated.</p>
`project`|**[Project](toloka.client.project.Project.md)**|<p>The project with new parameters.</p>

* **Returns:**

  enum value that describes the level of difference between the current project
and the project that would be created if the update is applied.

* **Return type:**

  [ProjectUpdateDifferenceLevel](toloka.client.project.ProjectUpdateDifferenceLevel.md)
