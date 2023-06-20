# RadioGroupFieldV1
`toloka.client.project.template_builder.fields.RadioGroupFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/fields.py#L408)

```python
RadioGroupFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    options: Optional[Union[BaseComponent, List[Union[BaseComponent, GroupFieldOption]]]] = None,
    *,
    disabled: Optional[Union[BaseComponent, bool]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A component for selecting one value out of several options.


For more information, see [field.radio-group](https://toloka.ai/docs/template-builder/reference/field.radio-group).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`options`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [GroupFieldOption](toloka.client.project.template_builder.fields.GroupFieldOption.md)\]\]\]\]**|<p>A list of options.</p>
`disabled`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Disabling the component:</p> <ul> <li>`False` — Selecting an option is allowed.</li> <li>`True` — Selecting an option is disabled.</li> </ul> <p></p><p>Default value: `False`.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>

**Examples:**


```python
radio_group_field = tb.fields.RadioGroupFieldV1(
    data=tb.data.OutputData(path='result'),
    options=[
        tb.fields.GroupFieldOption('Cat', 'cat'),
        tb.fields.GroupFieldOption('Dog', 'dog'),
    ],
    validation=tb.conditions.RequiredConditionV1()
)
```
