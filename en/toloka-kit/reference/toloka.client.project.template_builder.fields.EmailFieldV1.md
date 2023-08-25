# EmailFieldV1
`toloka.client.project.template_builder.fields.EmailFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/fields.py#L212)

```python
EmailFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    *,
    placeholder: Optional[Any] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A field for entering an email address.


For more information, see [field.email](https://toloka.ai/docs/template-builder/reference/field.email).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`placeholder`|**Optional\[Any\]**|<p>A text that is shown when no address is entered.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
