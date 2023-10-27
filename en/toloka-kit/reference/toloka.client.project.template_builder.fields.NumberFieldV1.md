# NumberFieldV1
`toloka.client.project.template_builder.fields.NumberFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/fields.py#L381)

```python
NumberFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    *,
    maximum: Optional[Union[BaseComponent, int]] = None,
    minimum: Optional[Union[BaseComponent, int]] = None,
    placeholder: Optional[Any] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A field for entering a number.


For more information, see [field.number](https://toloka.ai/docs/template-builder/reference/field.number).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`maximum`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), int\]\]**|<p>The maximum number that can be entered.</p>
`minimum`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), int\]\]**|<p>The minimum number that can be entered.</p>
`placeholder`|**Optional\[Any\]**|<p>A text that is shown if no number is entered.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
