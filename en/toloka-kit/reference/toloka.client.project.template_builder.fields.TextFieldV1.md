# TextFieldV1
`toloka.client.project.template_builder.fields.TextFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/fields.py#L468)

```python
TextFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    *,
    disabled: Optional[Union[BaseComponent, bool]] = None,
    placeholder: Optional[Any] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A field for entering a single text line.


For more information, see [field.text](https://toloka.ai/docs/template-builder/reference/field.text).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`disabled`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Disabling the field:</p> <ul> <li>`True` — A Toloker can&#x27;t enter a text in the field.</li> <li>`False` — Editing the field is allowed.</li> </ul> <p></p><p>Default value: `False`.</p>
`placeholder`|**Optional\[Any\]**|<p>A text that is shown if no value is entered.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
