# SideBySideLayoutV1
`toloka.client.project.template_builder.layouts.SideBySideLayoutV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/template_builder/layouts.py#L128)

```python
SideBySideLayoutV1(
    self,
    controls: Optional[BaseComponent] = None,
    items: Optional[Union[BaseComponent, List[BaseComponent]]] = None,
    *,
    min_item_width: Optional[Union[BaseComponent, float]] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A layout with several blocks of the same width on a single horizontal panel.


For more information, see [layout.side-by-side](https://toloka.ai/docs/template-builder/reference/layout.side-by-side).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`controls`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A component with controls.</p>
`items`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]\]\]**|<p>A list of blocks.</p>
`min_item_width`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The minimum width of a block, at least 400 pixels.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
