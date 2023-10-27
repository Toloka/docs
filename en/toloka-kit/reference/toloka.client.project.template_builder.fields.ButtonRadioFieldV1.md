# ButtonRadioFieldV1
`toloka.client.project.template_builder.fields.ButtonRadioFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/fields.py#L91)

```python
ButtonRadioFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    value_to_set: Optional[Any] = None,
    *,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A button to choose an answer.


For more information, see [field.button-radio](https://toloka.ai/docs/template-builder/reference/field.button-radio).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`value_to_set`|**Optional\[Any\]**|<p>A value to write to data.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
