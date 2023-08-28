# TextareaFieldV1
`toloka.client.project.template_builder.fields.TextareaFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/fields.py#L519)

```python
TextareaFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    *,
    disabled: Optional[Union[BaseComponent, bool]] = None,
    placeholder: Optional[Any] = None,
    resizable: Optional[Union[BaseComponent, bool]] = None,
    rows: Optional[Union[BaseComponent, float]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A field for entering multiline text.


For more information, see [field.textarea](https://toloka.ai/docs/template-builder/reference/field.textarea).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`disabled`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<ul> <li>`False` — A Toloker can edit the field.</li> <li>`True` — The field is disabled.</li> </ul> <p>Default value: `False`.</p>
`placeholder`|**Optional\[Any\]**|<p>A text that is shown if the field is empty.</p>
`resizable`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<ul> <li>`True` — A Toloker can change the height of the field.</li> <li>`False` — The field is not resizable.</li> </ul> <p>Default value: `True`.</p>
`rows`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The height of the field in text lines.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
