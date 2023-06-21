# App
`toloka.client.app.App` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/app/__init__.py#L93)

```python
App(
    self,
    *,
    id: Optional[str] = None,
    name: Optional[str] = None,
    image: Optional[str] = None,
    description: Optional[str] = None,
    constraints_description: Optional[str] = None,
    default_item_price: Optional[Decimal] = None,
    param_spec: Optional[Dict] = None,
    input_spec: Optional[Dict[str, FieldSpec]] = None,
    output_spec: Optional[Dict[str, FieldSpec]] = None,
    examples: Optional[Any] = None,
    input_format_info: Optional[Dict] = None
)
```

An [App](https://toloka.ai/docs/api/apps-reference/#tag--app) solution.


Each App solution targets specific type of tasks which can be solved using Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the App solution.</p>
`name`|**Optional\[str\]**|<p>The solution name.</p>
`image`|**Optional\[str\]**|<p>A link to the solution interface preview image.</p>
`description`|**Optional\[str\]**|<p>The solution description.</p>
`constraints_description`|**Optional\[str\]**|<p>The description of limitations.</p>
`default_item_price`|**Optional\[Decimal\]**|<p>The default cost of one annotated item.</p>
`param_spec`|**Optional\[Dict\]**|<p>The specification of parameters used to create a project.</p>
`input_spec`|**Optional\[Dict\[str, [FieldSpec](toloka.client.project.field_spec.FieldSpec.md)\]\]**|<p>The schema of solution input data.</p>
`output_spec`|**Optional\[Dict\[str, [FieldSpec](toloka.client.project.field_spec.FieldSpec.md)\]\]**|<p>The schema of solution output data.</p>
`examples`|**Optional\[Any\]**|<p>Example description of tasks which can be solved with this solution.</p>
`input_format_info`|**Optional\[Dict\]**|<p>Information about the input data format.</p>
