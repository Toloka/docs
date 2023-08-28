# ImageAnnotationHotkeysPluginV1
`toloka.client.project.template_builder.plugins.ImageAnnotationHotkeysPluginV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/plugins.py#L25)

```python
ImageAnnotationHotkeysPluginV1(
    self,
    *,
    cancel: Optional[Union[BaseComponent, str]] = None,
    confirm: Optional[Union[BaseComponent, str]] = None,
    labels: Optional[Union[BaseComponent, List[str]]] = None,
    point: Optional[str] = None,
    polygon: Optional[str] = None,
    rectangle: Optional[str] = None,
    select: Optional[str] = None,
    version: Optional[str] = '1.0.0'
)
```

Hotkeys for the [ImageAnnotationFieldV1](toloka.client.project.template_builder.fields.ImageAnnotationFieldV1.md) component.


For more information, see [plugin.field.image-annotation.hotkeys](https://toloka.ai/docs/template-builder/reference/plugin.field.image-annotation.hotkeys).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`cancel`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>A hotkey for canceling area creation.</p>
`confirm`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>A hotkey for confirming area creation.</p>
`labels`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[str\]\]\]**|<p>A list of hotkeys for choosing area labels.</p>
`modes`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Mode](toloka.client.project.template_builder.plugins.ImageAnnotationHotkeysPluginV1.Mode.md)\]\]**|<p>Hotkeys for switching selection modes.</p>
