# Marker
`toloka.client.project.template_builder.view.MapViewV1.Marker` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/view.py#L462)

```python
Marker(
    self,
    position: Optional[Union[BaseComponent, str]] = None,
    *,
    color: Optional[Union[BaseComponent, str]] = None,
    label: Optional[Union[BaseComponent, str]] = None
)
```

A map marker.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`position`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>The coordinates of the marker. You can use:</p> <ul> <li>A string. For example, `29.748713,-95.404287`.</li> <li>The [LocationData](toloka.client.project.template_builder.data.LocationData.md) to set Toloker&#x27;s current position.</li> </ul>
`color`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>The marker color. Use the hexadecimal values preceded by the `#`. For example, `#f00` makes the marker red.</p>
`label`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>A marker label.</p>
