# Project
`toloka.client.project.Project` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/__init__.py#L63)

```python
Project(
    self,
    *,
    public_name: Optional[str] = None,
    public_description: Optional[str] = None,
    task_spec: Optional[TaskSpec] = None,
    assignments_issuing_type: Union[AssignmentsIssuingType, str] = AssignmentsIssuingType.AUTOMATED,
    assignments_issuing_view_config: Optional[AssignmentsIssuingViewConfig] = None,
    assignments_automerge_enabled: Optional[bool] = None,
    max_active_assignments_count: Optional[int] = None,
    quality_control: Optional[QualityControl] = None,
    metadata: Optional[Dict[str, List[str]]] = None,
    status: Optional[ProjectStatus] = None,
    created: Optional[datetime] = None,
    id: Optional[str] = None,
    public_instructions: Optional[str] = None,
    private_comment: Optional[str] = None,
    localization_config: Optional[LocalizationConfig] = None
)
```

Top-level object in Toloka that describes one requester's objective.


If your task is complex, consider to [decompose](https://toloka.ai/docs/guide/solution-architecture) it into several projects.
For example, one project finds images with some objects, another project describes image segmentation, and the third project checks this segmentation.

In a project, you set properties for tasks and responses:
* Input data parameters describe what kind of input data you have: images, text, and other.
* Output data parameters describe Tolokers' responses. They are used to validate a data type, range of values, string length, and so on.
* Task interface. To learn how to define the appearance of tasks, see [Task interface](https://toloka.ai/docs/guide/spec) in the guide.

You upload [tasks](toloka.client.task.Task.md) to project [pools](toloka.client.pool.Pool.md) and [training pools](toloka.client.training.Training.md).
They are grouped into [task suites](toloka.client.task_suite.TaskSuite.md) and assigned to Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`public_name`|**Optional\[str\]**|<p>The name of the project. Visible to Tolokers.</p>
`public_description`|**Optional\[str\]**|<p>The description of the project. Visible to Tolokers.</p>
`public_instructions`|**Optional\[str\]**|<p>Instructions for Tolokers describe what to do in the tasks. You can use any HTML markup in the instructions.</p>
`private_comment`|**Optional\[str\]**|<p>Comments about the project. Visible only to the requester.</p>
`task_spec`|**Optional\[[TaskSpec](toloka.client.project.task_spec.TaskSpec.md)\]**|<p>Input and output data specification and the task interface. The interface can be defined with HTML, CSS, and JS or using the [Template Builder](https://toloka.ai/docs/template-builder/) components.</p>
`assignments_issuing_type`|**[AssignmentsIssuingType](toloka.client.project.Project.AssignmentsIssuingType.md)**|<p>Settings for assigning tasks. </p><p>Default value: `AUTOMATED`.</p>
`assignments_issuing_view_config`|**Optional\[[AssignmentsIssuingViewConfig](toloka.client.project.Project.AssignmentsIssuingViewConfig.md)\]**|<p>The configuration of a task view on a map. Provide it if `assignments_issuing_type=MAP_SELECTOR`.</p>
`assignments_automerge_enabled`|**Optional\[bool\]**|<p>[Merging tasks](https://toloka.ai/docs/api/tasks) control.</p>
`max_active_assignments_count`|**Optional\[int\]**|<p>The number of task suites simultaneously assigned to a Toloker. Note, that Toloka counts assignments having the `ACTIVE` status only.</p>
`quality_control`|**Optional\[[QualityControl](toloka.client.quality_control.QualityControl.md)\]**|<p>[Quality control](https://toloka.ai/docs/guide/project-qa) rules.</p>
`localization_config`|**Optional\[[LocalizationConfig](toloka.client.project.localization.LocalizationConfig.md)\]**|<p>Translations to other languages.</p>
`metadata`|**Optional\[Dict\[str, List\[str\]\]\]**|<p>Additional information about the project.</p>
`id`|**Optional\[str\]**|<p>The ID of the project. Read-only field.</p>
`status`|**Optional\[[ProjectStatus](toloka.client.project.Project.ProjectStatus.md)\]**|<p>A project status. Read-only field.</p>
`created`|**Optional\[datetime\]**|<p>The UTC date and time when the project was created. Read-only field.</p>

**Examples:**

Creating a new project.

```python
new_project = toloka.client.project.Project(
    assignments_issuing_type=toloka.client.project.Project.AssignmentsIssuingType.AUTOMATED,
    public_name='My best project',
    public_description='Describe the picture',
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
## Methods Summary

| Method | Description |
| :------| :-----------|
[add_requester_translation](toloka.client.project.Project.add_requester_translation.md)| Adds a project interface translation to other language.
[set_default_language](toloka.client.project.Project.set_default_language.md)| Sets the main language used in the project parameters.
