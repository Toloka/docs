# PhoneNumberFieldV1
`toloka.client.project.template_builder.fields.PhoneNumberFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/fields.py#L398)

```python
PhoneNumberFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    *,
    placeholder: Optional[Union[BaseComponent, str]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A field for entering a phone number.


For more information, see [field.phone-number](https://toloka.ai/docs/template-builder/reference/field.phone-number).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`placeholder`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>A text that is shown if no phone number is entered.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
