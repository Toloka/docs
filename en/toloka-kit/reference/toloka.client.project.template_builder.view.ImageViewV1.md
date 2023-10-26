# ImageViewV1
`toloka.client.project.template_builder.view.ImageViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/view.py#L221)

```python
ImageViewV1(
    self,
    url: Optional[Any] = None,
    *,
    full_height: Optional[Union[BaseComponent, bool]] = None,
    max_width: Optional[Union[BaseComponent, float]] = None,
    min_width: Optional[Union[BaseComponent, float]] = None,
    no_border: Optional[Union[BaseComponent, bool]] = None,
    no_lazy_load: Optional[Union[BaseComponent, bool]] = None,
    popup: Optional[Union[BaseComponent, bool]] = None,
    ratio: Optional[Union[BaseComponent, List[Union[BaseComponent, float]]]] = None,
    rotatable: Optional[Union[BaseComponent, bool]] = None,
    scrollable: Optional[Union[BaseComponent, bool]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A component for displaying an image.


For more information, see [view.image](https://toloka.ai/docs/template-builder/reference/view.image).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`url`|**Optional\[Any\]**|<p>The URL of the image.</p>
`full_height`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>If `True`, the component takes up all the vertical free space. Note, that the minimum height required by the component is 400 pixels.</p>
`max_width`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The maximum width of the component in pixels.</p>
`min_width`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The minimum width of the component in pixels. It takes priority over the `max_width`.</p>
`no_border`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Displaying borders around the image.</p> <ul> <li>`True` — The borders are hidden.</li> <li>`False` — The borders are visible.</li> </ul> <p></p><p>Default value: `True`.</p>
`no_lazy_load`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Loading mode:</p> <ul> <li>`False` — The component starts loading the image when the component becomes visible to a Toloker.</li> <li>`True` — The image is loaded immediately. This mode is useful for icons.</li> </ul> <p></p><p>Default value: `False` — lazy loading is enabled.</p>
`popup`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>If `True`, a Toloker can open a full sized image in a popup. It is a default behavior.</p>
`ratio`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]\]\]**|<p>A list with the aspect ratio of the component. Specify the relative width first and then the relative height. This setting is not used if `full_height=True`.</p>
`rotatable`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>If `True`, an image can be rotated.</p>
`scrollable`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>The way of displaying an image which is larger than the component:</p> <ul> <li>`True` — Scroll bars are shown.</li> <li>`False` — The image is scaled to fit the component.</li> </ul> <p>Note, that images in SVG format with no size specified always fit the component.</p>
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
