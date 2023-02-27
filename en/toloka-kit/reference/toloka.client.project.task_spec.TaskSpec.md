# TaskSpec
`toloka.client.project.task_spec.TaskSpec` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/project/task_spec.py#L8)

```python
TaskSpec(
    self,
    *,
    input_spec: Optional[Dict[str, FieldSpec]] = None,
    output_spec: Optional[Dict[str, FieldSpec]] = None,
    view_spec: Optional[ViewSpec] = None
)
```

Task interface description and input and output data specifications.


Input and output data specifications are dictionaries.
Field IDs are keys and field specifications are values.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`input_spec`|**Optional\[Dict\[str, [FieldSpec](toloka.client.project.field_spec.FieldSpec.md)\]\]**|<p>Input data specification.</p>
`output_spec`|**Optional\[Dict\[str, [FieldSpec](toloka.client.project.field_spec.FieldSpec.md)\]\]**|<p>Output data specification.</p>
`view_spec`|**Optional\[[ViewSpec](toloka.client.project.view_spec.ViewSpec.md)\]**|<p>The description of the task interface.</p>
