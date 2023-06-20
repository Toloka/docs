# DistanceConditionV1
`toloka.client.project.template_builder.conditions.DistanceConditionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/conditions.py#L86)

```python
DistanceConditionV1(
    self,
    from_: Optional[Union[BaseComponent, str]] = None,
    to_: Optional[Union[BaseComponent, str]] = None,
    max: Optional[Union[BaseComponent, float]] = None,
    *,
    hint: Optional[Any] = None,
    version: Optional[str] = '1.0.0'
)
```

Checks a distance between two coordinates.


For more information, see [condition.distance](https://toloka.ai/docs/template-builder/reference/condition.distance).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`from_`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>The first point.</p>
`to_`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>The second point.</p>
`max`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The maximum distance in meters.</p>
`hint`|**Optional\[Any\]**|<p>A hint that is shown if the condition is not met.</p>

**Examples:**

The following condition gets Toloker's [location](toloka.client.project.template_builder.data.LocationData.md)
and checks that it is near the task location.

```python
distance_condition = tb.conditions.DistanceConditionV1(
    tb.data.LocationData(),
    tb.data.InputData('coordinates'),
    500,
    hint='You are too far from the destination coordinates.',
),
```
