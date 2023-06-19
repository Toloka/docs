# clone_project
`toloka.client.TolokaClient.clone_project` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L1300)

```python
clone_project(
    self,
    project_id: str,
    reuse_controllers: bool = True
)
```

Clones a project and all pools and trainings inside it.


`clone_project` emulates cloning behavior via Toloka interface. Note that it calls several API methods. If some method fails then the project may be partially cloned.

Important notes:
* No tasks are cloned.
* The expiration date is not changed in the new project.
* The same skills are used.
* If `reuse_controllers` is `True`, quality control collectors monitor both projects.
    For example, the `fast_submitted_count` rule counts fast responses in the cloned and new projects together.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`project_id`|**str**|<p>The ID of the project to be cloned.</p>
`reuse_controllers`|**bool**|<ul> <li>`True` — Use same quality controllers in cloned and created projects.</li> <li>`False` — Use separate quality controllers.</li> </ul> <p></p><p>Default value: `True`.</p>

* **Returns:**

  Created project, pools and trainings.

* **Return type:**

  [CloneResults](toloka.client.clone_results.CloneResults.md)

**Examples:**


```python
project, pools, trainings = toloka_client.clone_project('123')
# add tasks in pools and trainings
```
