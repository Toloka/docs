# GroupViewV1
`toloka.client.project.template_builder.view.GroupViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/view.py#L183)

```python
GroupViewV1(
    self,
    content: Optional[BaseComponent] = None,
    *,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A view with a frame.


For more information, see [view.group](https://toloka.ai/docs/template-builder/reference/view.group).

    Attributes:
        content: A content.
        label: A header.
        hint: A hint. To insert a line break in the hint, use `\n`.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
