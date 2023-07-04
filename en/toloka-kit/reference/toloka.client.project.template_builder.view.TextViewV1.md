# TextViewV1
`toloka.client.project.template_builder.view.TextViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/view.py#L405)

```python
TextViewV1(
    self,
    content: Optional[Any] = None,
    *,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A view for displaying a text.


For more information, see [view.text](https://toloka.ai/docs/template-builder/reference/view.text).

    Attributes:
        content: The text. To insert a new line, use `\n`.

    Example:
```python
text_view = tb.view.TextViewV1(tb.data.InputData('input_field_name'), label='My label:')
```


## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
