# CheckboxFieldV1
`toloka.client.project.template_builder.fields.CheckboxFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/project/template_builder/fields.py#L142)

```python
CheckboxFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    *,
    disabled: Optional[Union[BaseComponent, bool]] = None,
    preserve_false: Optional[Union[BaseComponent, bool]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

Checkbox.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Data with values that will be processed or changed.</p>
`disabled`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Property that disables the component. If `True`, the component will not be unavailable.</p>
`preserve_false`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Property that specifies whether to return false values in the results. By default, if the component returns `False`, this result will not be added to the output. To add `False` to the results, specify `preserve_false=True`.</p>
`hint`|**Optional\[Any\]**|<p>Hint text.</p>
`label`|**Optional\[Any\]**|<p>Label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation based on condition.</p>
