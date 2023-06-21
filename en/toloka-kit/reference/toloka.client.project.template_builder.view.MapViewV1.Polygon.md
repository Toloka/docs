# Polygon
`toloka.client.project.template_builder.view.MapViewV1.Polygon` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/project/template_builder/view.py#L473)

```python
Polygon(
    self,
    points: Optional[Union[BaseComponent, List[Union[BaseComponent, str]]]] = None,
    *,
    color: Optional[Union[BaseComponent, str]] = None
)
```

A map polygon.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`points`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]\]\]**|<p>A list of polygon coordinates. Specify the coordinates in the string format, for example `29.748713,-95.404287`.</p>
`color`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>The color of the polygon. Use the hexadecimal values preceded by the `#`. For example, `#f00` makes the polygon red.</p>
