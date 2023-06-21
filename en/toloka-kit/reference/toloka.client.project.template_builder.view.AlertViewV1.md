# AlertViewV1
`toloka.client.project.template_builder.view.AlertViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/template_builder/view.py#L78)

```python
AlertViewV1(
    self,
    content: Optional[BaseComponent] = None,
    *,
    theme: Optional[Union[BaseComponent, Theme]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A view used to highlight important information.


For more information, see [view.alert](https://toloka.ai/docs/template-builder/reference/view.alert).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`content`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>The content.</p>
`theme`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Theme](toloka.client.project.template_builder.view.AlertViewV1.Theme.md)\]\]**|<p>The theme that sets the background color. The default color is blue.</p>
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
