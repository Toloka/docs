# MapViewV1
`toloka.client.project.template_builder.view.MapViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/view.py#L447)

```python
MapViewV1(
    self,
    center: Optional[Union[BaseComponent, str]] = None,
    *,
    markers: Optional[Union[BaseComponent, List[Union[BaseComponent, Marker]]]] = None,
    polygons: Optional[Union[BaseComponent, List[Union[BaseComponent, Polygon]]]] = None,
    zoom: Optional[Union[BaseComponent, int]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A component for displaying a map.


For more information, see [view.map](https://toloka.ai/docs/template-builder/reference/view.map).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`center`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>The coordinates of the map center. You can use:</p> <ul> <li>A string. For example, `29.748713,-95.404287`</li> <li>The [LocationData](toloka.client.project.template_builder.data.LocationData.md) to set Toloker&#x27;s current position.</li> </ul>
`markers`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Marker](toloka.client.project.template_builder.view.MapViewV1.Marker.md)\]\]\]\]**|<p>A list of map markers.</p>
`polygons`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Polygon](toloka.client.project.template_builder.view.MapViewV1.Polygon.md)\]\]\]\]**|<p>A list of areas highlighted on the map.</p>
`zoom`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), int\]\]**|<p>An initial map scale. Use values from 0 to 19. Higher values zoom in the map.</p>
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
