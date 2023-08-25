# CheckboxGroupFieldV1
`toloka.client.project.template_builder.fields.CheckboxGroupFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/fields.py#L163)

```python
CheckboxGroupFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    options: Optional[Union[BaseComponent, List[Union[BaseComponent, GroupFieldOption]]]] = None,
    *,
    disabled: Optional[Union[BaseComponent, bool]] = None,
    preserve_false: Optional[Union[BaseComponent, bool]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A group of checkboxes.


This component creates a dictionary in the output data. Values from `options` are used as keys in the dictionary.

For more information, see [field.checkbox-group](https://toloka.ai/docs/template-builder/reference/field.checkbox-group).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`options`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [GroupFieldOption](toloka.client.project.template_builder.fields.GroupFieldOption.md)\]\]\]\]**|<p>A list of options.</p>
`disabled`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Disabling the checkbox group.</p>
`preserve_false`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<ul> <li>`False` — If a checkbox from the group is not selected then its key is not added to the dictionary.</li> <li>`True` — The output dictionary contains all keys whether checkboxes are selected or not.</li> </ul> <p></p><p>Default value: `False`.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
