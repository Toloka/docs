# SidebarLayoutV1
`toloka.client.project.template_builder.layouts.SidebarLayoutV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/layouts.py#L145)

```python
SidebarLayoutV1(
    self,
    content: Optional[BaseComponent] = None,
    controls: Optional[BaseComponent] = None,
    *,
    controls_width: Optional[Union[BaseComponent, float]] = None,
    extra_controls: Optional[BaseComponent] = None,
    min_width: Optional[Union[BaseComponent, float]] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A layout with a main content block and a panel with controls.


The component supports modes:
    * Widescreen — The control panel is placed to the right of the main block.
    * Compact — The controls are placed under the main block and stretch to the entire width.

For more information, see [layout.sidebar](https://toloka.ai/docs/template-builder/reference/layout.sidebar).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`content`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>The main block.</p>
`controls`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>The control panel.</p>
`controls_width`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The width in pixels of the control panel in the widescreen mode. </p><p>Default value: `200`.</p>
`extra_controls`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>An additional panel with controls. It is placed below the controls.</p>
`min_width`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The minimum width in pixels of the component in a widescreen mode. If the component width is less than the specified value, the interface switches to the compact mode. </p><p>Default value: `400`.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
