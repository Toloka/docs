# SelectFieldV1
`toloka.client.project.template_builder.fields.SelectFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/template_builder/fields.py#L438)

```python
SelectFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    options: Optional[Union[BaseComponent, List[Union[BaseComponent, Option]]]] = None,
    *,
    placeholder: Optional[Any] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A field for selecting from a drop-down list of options.


For more information, see [field.select](https://toloka.ai/docs/template-builder/reference/field.select).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`options`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Option](toloka.client.project.template_builder.fields.SelectFieldV1.Option.md)\]\]\]\]**|<p>A list of options.</p>
`placeholder`|**Optional\[Any\]**|<p>A text that is shown if no option is selected.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
