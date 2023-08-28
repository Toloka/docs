# BaseViewV1
`toloka.client.project.template_builder.view.BaseViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/view.py#L52)

```python
BaseViewV1(
    self,
    *,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A base class for components that present data, such as a text, list, audio player, or image.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
