# ImageAnnotationFieldV1
`toloka.client.project.template_builder.fields.ImageAnnotationFieldV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/template_builder/fields.py#L245)

```python
ImageAnnotationFieldV1(
    self,
    data: Optional[BaseComponent] = None,
    image: Optional[Union[BaseComponent, str]] = None,
    *,
    disabled: Optional[Union[BaseComponent, bool]] = None,
    full_height: Optional[Union[BaseComponent, bool]] = None,
    labels: Optional[Union[BaseComponent, List[Union[BaseComponent, Label]]]] = None,
    min_width: Optional[Union[BaseComponent, float]] = None,
    ratio: Optional[Union[BaseComponent, List[Union[BaseComponent, float]]]] = None,
    shapes: Optional[Union[BaseComponent, Dict[Union[BaseComponent, Shape], Union[BaseComponent, bool]]]] = None,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A component for annotating areas in an image.


For more information, see [field.image-annotation](https://toloka.ai/docs/template-builder/reference/field.image-annotation).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>A data path.</p>
`image`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), str\]\]**|<p>The URL of the image.</p>
`disabled`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>Disabling the component:</p> <ul> <li>`False` — Annotating is allowed.</li> <li>`True` — Annotating is disabled.</li> </ul> <p></p><p>Default value: `False`.</p>
`full_height`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]**|<p>If `True`, the component takes up all the vertical free space. Note, that the minimum height required by the component is 400 pixels.</p>
`labels`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Label](toloka.client.project.template_builder.fields.ImageAnnotationFieldV1.Label.md)\]\]\]\]**|<p>Labels used to classify image areas.</p>
`min_width`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]**|<p>The minimum width of the component in pixels.</p>
`ratio`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), List\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), float\]\]\]\]**|<p>A list with the aspect ratio of the component. Specify the relative width and then the height. This setting is not used if `full_height=True`.</p>
`shapes`|**Optional\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), Dict\[Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), [Shape](toloka.client.project.template_builder.fields.ImageAnnotationFieldV1.Shape.md)\], Union\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md), bool\]\]\]\]**|<p>Area selection modes: `point`, `polygon`, and `rectangle`. Use mode names as keys in the `shapes` dictionary. Modes set to `True` are available in the component. By default, all modes are available.</p>
`hint`|**Optional\[Any\]**|<p>A hint.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
