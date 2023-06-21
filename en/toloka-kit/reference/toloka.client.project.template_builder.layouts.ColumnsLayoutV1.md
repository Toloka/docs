# ColumnsLayoutV1
`toloka.client.project.template_builder.layouts.ColumnsLayoutV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/template_builder/layouts.py#L56)

```python
ColumnsLayoutV1(
    self,
    items: Optional[Union[BaseComponent, List[BaseComponent]]] = None,
    *,
    full_height: Optional[Union[BaseComponent, bool]] = None,
    min_width: Optional[Union[BaseComponent, float]] = None,
    ratio: Optional[Union[BaseComponent, List[Union[BaseComponent, float]]]] = None,
    vertical_align: Optional[Union[BaseComponent, VerticalAlign]] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A layout with columns.


For more information, see [layout.columns](https://toloka.ai/docs/template-builder/reference/layout.columns).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]\]\]**|<p>A list of components. Every component is placed in an individual column.</p>
`full_height`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>A height mode:</p> <ul> <li>`True` — The component occupies all available vertical space. Columns have individual scrolling.</li> <li>`False` — The height of the component is determined by the highest column.</li> </ul>
`min_width`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The minimum width of the component when columns are used. If the component is narrower than `min_width`, then all content is shown in one column.</p>
`ratio`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]\]\]**|<p>A list of relative column widths.</p>
`vertical_align`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [VerticalAlign](toloka.client.project.template_builder.layouts.ColumnsLayoutV1.VerticalAlign.md)\]\]**|<p>The vertical alignment of column content.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
