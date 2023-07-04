# BaseFieldV1
`toloka.client.project.template_builder.fields.BaseFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/fields.py#L59)

```python
BaseFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    *,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A base class for input data fields.


Input fields are used to get data from Tolokers.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
