# CompareLayoutV1
`toloka.client.project.template_builder.layouts.CompareLayoutV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/layouts.py#L105)

```python
CompareLayoutV1(
    self,
    common_controls: Optional[BaseComponent] = None,
    items: Optional[Union[BaseComponent, List[Union[BaseComponent, CompareLayoutItem]]]] = None,
    *,
    min_width: Optional[Union[BaseComponent, float]] = None,
    wide_common_controls: Optional[Union[BaseComponent, bool]] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A layout for comparing several items.


For more information, see [layout.compare](https://toloka.ai/docs/template-builder/reference/layout.compare).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`common_controls`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A component containing common controls.</p>
`items`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [CompareLayoutItem](toloka.client.project.template_builder.layouts.CompareLayoutItem.md)\]\]\]\]**|<p>A list of items to be compared.</p>
`min_width`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The minimum width of the component in pixels. </p><p>Default value: `400`.</p>
`wide_common_controls`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<ul> <li>`True` — The common controls are stretched horizontally.</li> <li>`False` — The common controls are centered.</li> </ul> <p></p><p>Default value: `False`.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
