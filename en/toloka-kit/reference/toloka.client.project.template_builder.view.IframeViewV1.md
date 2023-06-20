# IframeViewV1
`toloka.client.project.template_builder.view.IframeViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/view.py#L198)

```python
IframeViewV1(
    self,
    url: Optional[Union[BaseComponent, str]] = None,
    *,
    full_height: Optional[Union[BaseComponent, bool]] = None,
    max_width: Optional[Union[BaseComponent, float]] = None,
    min_width: Optional[Union[BaseComponent, float]] = None,
    ratio: Optional[Union[BaseComponent, List[Union[BaseComponent, float]]]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A frame displaying a web page.


For more information, see [view.iframe](https://toloka.ai/docs/template-builder/reference/view.iframe).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`url`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>The URL of the web page.</p>
`full_height`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>If `True`, the component takes up all the vertical free space. Note, that the minimum height required by the component is 400 pixels.</p>
`max_width`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The maximum width of the component in pixels.</p>
`min_width`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The minimum width of the component in pixels. It takes priority over the `max_width`.</p>
`ratio`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]\]\]**|<p>A list with the aspect ratio of the component. Specify the relative width first and then the relative height. This setting is not used if `full_height=True`.</p>
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
