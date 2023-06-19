# AllConditionV1
`toloka.client.project.template_builder.conditions.AllConditionV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/conditions.py#L43)

```python
AllConditionV1(
    self,
    conditions: Optional[Union[BaseComponent, List[BaseComponent]]] = None,
    *,
    hint: Optional[Any] = None,
    version: Optional[str] = '1.0.0'
)
```

Checks that all nested conditions are met.


For more information, see [condition.all](https://toloka.ai/docs/template-builder/reference/condition.all).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`conditions`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]\]\]**|<p>A list of conditions.</p>
`hint`|**Optional\[Any\]**|<p>A hint that is shown if the condition is not met.</p>

**Examples:**


```python
coordinates_validation = tb.conditions.AllConditionV1(
    [
        tb.conditions.RequiredConditionV1(
            tb.data.OutputData('performer_coordinates'),
            hint="Couldn't get your coordinates. Please enable geolocation.",
        ),
        tb.conditions.DistanceConditionV1(
            tb.data.LocationData(),
            tb.data.InputData('coordinates'),
            500,
            hint='You are too far from the destination coordinates.',
        ),
    ],
)
```
